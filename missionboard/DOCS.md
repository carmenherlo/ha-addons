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

**Mi sitio:** tocando su avatar, cada niño entra en su paisaje: su casa, el buzón, el taller del cohete, el observatorio y la tienda.

![Mi sitio](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/place.webp)

**La tienda:** con sus estrellas, el niño hace un pedido, y los padres deciden cuándo llega.

![La tienda](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/shop.webp)

**El taller del cohete:** cada día con sus misiones hechas llena un depósito; con la semana completa, el cohete despega a por el premio de la semana.

![El taller del cohete](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/garage.webp)

**Zona de padres · Hoy:** cómo van los niños, lo que hay pendiente de dar y la semana de cada uno.

![Zona de padres · Hoy](https://raw.githubusercontent.com/carmenherlo/missionboard/main/screenshots/parents-today.webp)

## Uso

1. Instala el complemento y pulsa **Iniciar**. La primera instalación tarda unos minutos (descarga unos 450 MB).
2. Activa **Mostrar en la barra lateral** y ábrelo desde ahí.
3. También funciona directo en el navegador de la tablet: `http://homeassistant.local:8003` (o la IP del mini PC con `:8003`). Así lo pueden usar los usuarios que no son administradores, por ejemplo con una tarjeta **Página web** en un panel.

El código de padres por defecto es `1234`. Cámbialo en la zona de padres, en **Código de padres**.

Si la voz no se oye al principio, toca la pantalla una vez: algunos navegadores no dejan sonar nada hasta que se toca.

## Avisos de la tienda en el móvil

Cuando un niño compra algo en la tienda, el pedido llega a los móviles que tengan la app de Home Assistant, con botones: «Hoy», «Mañana» y «Entregado». Si llega el día y no se lo has dado, te lo recuerda. Los móviles se eligen en la zona de padres, en **Avisos al móvil** (con un botón para mandar un aviso de prueba); en **Tienda → Avisar al móvil** se encienden o apagan los avisos de los pedidos y la hora del recordatorio. Para ello el complemento pide acceso a la API de Home Assistant.

Si usas la versión *minimal* de la app de Home Assistant (la que no usa los servicios de Google), los avisos solo llegan cuando el móvil puede conectar con tu Home Assistant. Para recibirlos también fuera de casa, en la app ve a **Ajustes → App complementaria → Conexión persistente** y elige **Siempre** (gasta algo más de batería).

## Datos y copias de seguridad

Todos los datos se guardan dentro del complemento, así que las copias de seguridad de Home Assistant los incluyen.

Para traer los datos de otra instalación de Missionboard:

1. En la instalación antigua: **Zona de padres → Copia de seguridad → Descargar** (un archivo `.zip`).
2. En este complemento: **Zona de padres → Copia de seguridad → Restaurar** y elige ese `.zip`.

## Créditos

Icono: Glowing Star de Fluent Emoji, de Microsoft (licencia MIT).
