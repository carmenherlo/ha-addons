# Missionboard

Tablero de misiones, rutinas y premios para niños, con voz en español. Pensado para una tablet a pantalla completa.

## Uso

1. Instala el complemento y pulsa **Iniciar**. La primera instalación tarda unos minutos (descarga unos 450 MB).
2. Pulsa **Abrir interfaz web**, o abre en el navegador de la tablet `http://homeassistant.local:8003` (o la IP del mini PC con `:8003`).
3. Para tenerlo en un panel de Home Assistant, añade una tarjeta **Página web** con esa dirección.

No aparece en la barra lateral: la aplicación solo funciona en su propio puerto.

El código de padres por defecto es `1234`. Cámbialo en **Configurar**.

Si la voz no se oye al principio, toca la pantalla una vez: algunos navegadores no dejan sonar nada hasta que se toca.

## Datos y copias de seguridad

Todos los datos se guardan dentro del complemento, así que las copias de seguridad de Home Assistant los incluyen.

Para traer los datos de otra instalación de Missionboard:

1. En la instalación antigua: **Configurar → Copia de seguridad → Descargar** (un archivo `.zip`).
2. En este complemento: **Configurar → Copia de seguridad → Restaurar** y elige ese `.zip`.
