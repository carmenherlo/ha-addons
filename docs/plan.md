# Plan

## Estado

- **Space Race 0.1.3** funcionando en HA: barra lateral (Ingress) y puerto 8100 para usuarios no administradores.
- **Missionboard 0.1.0** creado (`missionboard/`), probado con Docker en el PC (arranca, `/api/health` ok, datos en `/data`). Sin icono todavía.
- **Siguiente paso:** push, instalarlo en HA, abrirlo en la tablet (`:8003`) y restaurar la copia de seguridad de la familia.

## La idea

Un repositorio de add-ons de Home Assistant para tener nuestras apps y juegos en la barra lateral de HA, sobre todo desde la tablet. Cada add-on solo empaqueta una app; el código de la app vive en su propio repo.

## Add-ons

| Add-on | Estado |
|---|---|
| `space-race/` | Hecho (0.1.3) |
| `missionboard/` | Creado (0.1.0), falta probar en HA |

## Decisiones tomadas

- **El código de cada app viene de su repo público en GitHub**, descargado al construir la imagen. HA no necesita credenciales.
- **Los archivos privados (avatares, fotos) nunca van a un repo.** Se copian a mano a la carpeta `share` de HA por Samba, y cada `DOCS.md` explica cómo.
- **Arquitectura `amd64`** (el mini PC).
- **Puerto propio además de Ingress** cuando lo tengan que usar usuarios no administradores (Space Race: 8100).
- **Missionboard sin Ingress, solo puerto 8003:** la app usa rutas absolutas (`/api`, `/static`) y no funciona bajo la subruta de Ingress. Sus datos van a `/data` para que entren en las copias de HA.

## Decisiones pendientes

- ¿Icono y logo para Missionboard?
