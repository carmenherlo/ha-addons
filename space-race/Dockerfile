# Same steps as the game's own Dockerfile, but the code comes from its public GitHub repo.
FROM python:3.12-slim

ARG GAME_REPO=https://github.com/carmenherlo/space-race
ARG GAME_REF=main

# Avatars from HA's share folder (Samba); the voice's cache in the add-on's own /data.
ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    SPACE_RACE_AVATARS=/share/space-race/avatars \
    SPACE_RACE_CACHE=/data/cache

WORKDIR /app

# Dependencies first: this layer is reused while requirements.txt does not change.
ADD ${GAME_REPO}/raw/${GAME_REF}/requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Piper's Spanish voice model (about 77 MB), as in the game's Dockerfile.
ARG VOICE=es_ES-sharvard-medium
ARG VOICE_URL=https://huggingface.co/rhasspy/piper-voices/resolve/main/es/es_ES/sharvard/medium
RUN mkdir -p /opt/voices && python -c "import urllib.request as u; \
[u.urlretrieve(f'${VOICE_URL}/${VOICE}{ext}?download=true', f'/opt/voices/${VOICE}{ext}') \
 for ext in ('.onnx', '.onnx.json')]"

# The game's code: ADD re-downloads it on every build, so a new version is picked up.
ADD ${GAME_REPO}/archive/${GAME_REF}.tar.gz /tmp/game.tar.gz
RUN tar -xzf /tmp/game.tar.gz -C /tmp \
    && mv /tmp/space-race-*/app /tmp/space-race-*/content . \
    && rm -rf /tmp/game.tar.gz /tmp/space-race-*

CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
