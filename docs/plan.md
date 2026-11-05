# Plan

## Estado

- **Space Race 0.1.3** funcionando en HA: barra lateral (Ingress) y puerto 8100 para usuarios no administradores.
- **Missionboard 0.2.0** creado (`missionboard/`): barra lateral (Ingress) y puerto 8003. Probado con Docker en el PC. Sin icono/logo PNG todavía.
- **Siguiente paso:** push, instalarlo en HA, abrirlo en la barra lateral y en la tablet (`:8003`) y restaurar la copia de seguridad de la familia.

## La idea

Un repositorio de add-ons de Home Assistant para tener nuestras apps y juegos en la barra lateral de HA, sobre todo desde la tablet. Cada add-on solo empaqueta una app; el código de la app vive en su propio repo.

## Add-ons

| Add-on | Estado |
|---|---|
| `space-race/` | Hecho (0.1.3) |
| `missionboard/` | Creado (0.2.0), falta probar en HA |

## Decisiones tomadas

- **El código de cada app viene de su repo público en GitHub**, descargado al construir la imagen. HA no necesita credenciales.
- **Los archivos privados (avatares, fotos) nunca van a un repo.** Se copian a mano a la carpeta `share` de HA por Samba, y cada `DOCS.md` explica cómo.
- **Arquitectura `amd64`** (el mini PC).
- **Puerto propio además de Ingress** cuando lo tengan que usar usuarios no administradores (Space Race: 8100).
- **Ingress necesita rutas relativas en la app** (Space Race y Missionboard las usan). Los datos de Missionboard van a `/data` para que entren en las copias de HA.

## Decisiones pendientes

- ¿Icono y logo para Missionboard?
