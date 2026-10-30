# Home Assistant add-ons

Complementos (add-ons) de Home Assistant para los juegos y apps de casa.

| Add-on | Qué es |
|---|---|
| `space-race/` | Space Race, juego de tablero en español para 1–6 jugadores (en preparación) |

## Instalar en Home Assistant

1. Ajustes → Complementos → Tienda de complementos.
2. ⋮ (arriba a la derecha) → Repositorios → pegar la URL de este repositorio → Añadir.
3. Buscar el add-on, Instalar, Iniciar.
4. Activar "Mostrar en la barra lateral" para abrirlo desde la tablet.

## Cómo está hecho

Este repositorio **solo empaqueta** las apps: cada carpeta tiene la descripción del add-on (`config.yaml`) y su `Dockerfile`. El código de cada app vive en su propio repositorio y no sabe nada de Home Assistant.
