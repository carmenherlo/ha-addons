# Changelog

## 0.5.0

- The shop as orders on their way: the child sees a truck and how many nights are left, and the parcel arriving when a parent hands it over.
- Each order reaches the parents' phones (Home Assistant companion app) with buttons: "Hoy", "Mañana", "Ya se lo di". Phones chosen in Configurar → Tienda. The add-on now asks for access to Home Assistant's API.

## 0.4.1

- With four children or more, the "Zona de padres" button could not be tapped; they now fit in one row.

## 0.4.0

- The family's own avatars: uploaded in Configurar → Avatares (PNG or WebP), with any ring colour. Kept in `/data/avatars/` and in the app's backup.

## 0.3.0

- Family missions (mission → task → step), each switched on per child; routines built on a mission's tasks.
- Starts from scratch: data from before 0.3.0 is copied to `/data/backups/` and replaced by the examples (songs are kept).
- Ajustes: seasons and their backgrounds, the children's home and the route as a turning wheel.
- Times always in 24 hours; stars can be given to a child from the parents' zone.

## 0.2.0

- In HA's sidebar (Ingress); port 8003 stays for non-admin users.
- Icon and logo (Glowing Star from Fluent Emoji by Microsoft, MIT).

## 0.1.0

- First version: Missionboard on its own port (8003), with Piper's voice and data in the add-on's `/data`.
