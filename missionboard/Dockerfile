# Same steps as the app's own Dockerfile, but the code comes from its public GitHub repo.
FROM python:3.12-slim

ARG APP_REPO=https://github.com/carmenherlo/missionboard
ARG APP_REF=main

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1

WORKDIR /srv

# Dependencies first: this layer is reused while requirements.txt does not change.
ADD ${APP_REPO}/raw/${APP_REF}/requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Piper's Spanish voice model, as in the app's Dockerfile.
ARG VOICE=es_ES-sharvard-medium
ARG VOICE_URL=https://huggingface.co/rhasspy/piper-voices/resolve/main/es/es_ES/sharvard/medium
RUN mkdir -p /opt/voices && python -c "import urllib.request as u; \
[u.urlretrieve(f'${VOICE_URL}/${VOICE}{ext}?download=true', f'/opt/voices/${VOICE}{ext}') \
 for ext in ('.onnx', '.onnx.json')]"

# The app's code: ADD re-downloads it on every build, so a new version is picked up.
ADD ${APP_REPO}/archive/${APP_REF}.tar.gz /tmp/app.tar.gz
RUN tar -xzf /tmp/app.tar.gz -C /tmp \
    && mv /tmp/missionboard-*/app . \
    && rm -rf /tmp/app.tar.gz /tmp/missionboard-*

# Data in the add-on's /data, so HA backups include it.
ENV MISSIONBOARD_VOICE_MODEL=/opt/voices/${VOICE}.onnx \
    MISSIONBOARD_DATA_DIR=/data

EXPOSE 8003
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8003"]
