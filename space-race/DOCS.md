# Space Race

Juego de tablero en español para 1 a 6 jugadores, por turnos, en una sola tablet u ordenador.

## Uso

1. Instala el complemento y pulsa **Iniciar**.
2. Activa **Mostrar en la barra lateral**.
3. Ábrelo desde la barra lateral de Home Assistant (por ejemplo, en la tablet).

Si la voz o los sonidos no se oyen al principio, toca la pantalla una vez: algunos navegadores no dejan sonar nada hasta que se toca.

## Avatares

Los avatares no vienen con el complemento: se copian a mano por la red de casa.

1. En Home Assistant, instala el complemento **Samba share**, ponle usuario y contraseña, e inícialo.
2. En el ordenador, abre en el explorador de archivos `smb://homeassistant.local/share` (o la IP del mini PC).
3. Crea la carpeta `space-race/avatars` y copia ahí las imágenes y `colors.yaml`.
4. Reinicia el complemento Space Race.

Sin avatares el juego funciona igual, solo que no hay imágenes para elegir.
