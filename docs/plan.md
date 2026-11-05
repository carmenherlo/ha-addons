# Plan

## Estado

- **Space Race 0.1.3** funcionando en HA: barra lateral (Ingress) y puerto 8100 para usuarios no administradores.
- **Siguiente paso:** empezar un add-on nuevo. Hace falta: la app, su repo público en GitHub y cómo se arranca (su `Dockerfile` o el comando y el puerto).

## La idea

Un repositorio de add-ons de Home Assistant para tener nuestras apps y juegos en la barra lateral de HA, sobre todo desde la tablet. Cada add-on solo empaqueta una app; el código de la app vive en su propio repo.

## Add-ons

| Add-on | Estado |
|---|---|
| `space-race/` | Hecho (0.1.3) |

## Decisiones tomadas

- **El código de cada app viene de su repo público en GitHub**, descargado al construir la imagen. HA no necesita credenciales.
- **Los archivos privados (avatares, fotos) nunca van a un repo.** Se copian a mano a la carpeta `share` de HA por Samba, y cada `DOCS.md` explica cómo.
- **Arquitectura `amd64`** (el mini PC).
- **Puerto propio además de Ingress** cuando lo tengan que usar usuarios no administradores (Space Race: 8100).

## Decisiones pendientes

- Ninguna por ahora.
