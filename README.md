# Home Assistant add-ons

Home Assistant add-ons for the games and apps we use at home. Each add-on packages one app so it opens from HA's sidebar.

| Add-on | What it is |
|---|---|
| `space-race/` | Space Race, a Spanish board game for 1–6 players (in progress) |

## Install in Home Assistant

1. Settings → Apps → App store (called "Add-ons" in older versions).
2. ⋮ (top right) → Repositories → paste this repository's URL → Add.
3. Find the add-on, Install, Start.
4. Turn on "Show in sidebar" to open it from the tablet.

You need an administrator user to add the repository and install add-ons.

## How it works

This repository **only packages** the apps: each folder has the add-on's description (`config.yaml`) and its `Dockerfile`. Each app's code lives in its own repository and knows nothing about Home Assistant.

To add a new app, create a folder for it next to `space-race/` and add a row to the table above.
