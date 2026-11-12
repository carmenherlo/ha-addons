# Missionboard

Tablero de misiones, rutinas y premios para niños, con voz en español. Pensado para una tablet a pantalla completa.

![El inicio: cada niño con su avatar](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/home.webp)

## Cómo se ve

**La ruta del niño:** sus misiones en una rueda.

![La ruta del niño](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/route.webp)

**Una misión:** cada tarea se marca con un toque; las pistas recuerdan lo que incluye.

![Una misión](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/mission.webp)

**Una rutina en marcha:** el reloj con el tramo de cada parte, lo que toca ahora y los niños.

![Una rutina en marcha](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/routine.webp)

**El premio del día:** la ruleta, al completar todas las misiones.

![El premio del día](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/prize.webp)

**Zona de padres:** todo se configura desde la propia app.

![Editar una misión](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/parents-mission.webp)

## Uso

1. Instala el complemento y pulsa **Iniciar**. La primera instalación tarda unos minutos (descarga unos 450 MB).
2. Activa **Mostrar en la barra lateral** y ábrelo desde ahí.
3. También funciona directo en el navegador de la tablet: `http://homeassistant.local:8003` (o la IP del mini PC con `:8003`). Así lo pueden usar los usuarios que no son administradores, por ejemplo con una tarjeta **Página web** en un panel.

El código de padres por defecto es `1234`. Cámbialo en **Configurar**.

Si la voz no se oye al principio, toca la pantalla una vez: algunos navegadores no dejan sonar nada hasta que se toca.

## Datos y copias de seguridad

Todos los datos se guardan dentro del complemento, así que las copias de seguridad de Home Assistant los incluyen.

Para traer los datos de otra instalación de Missionboard:

1. En la instalación antigua: **Configurar → Copia de seguridad → Descargar** (un archivo `.zip`).
2. En este complemento: **Configurar → Copia de seguridad → Restaurar** y elige ese `.zip`.

## Créditos

Icono: Glowing Star de Fluent Emoji, de Microsoft (licencia MIT).
