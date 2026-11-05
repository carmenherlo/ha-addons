# CLAUDE.md

Guidance for Claude Code in this repository. The plan and current status are in `docs/plan.md`; read it first.

## What this is

A Home Assistant add-on repository (HA OS on a mini PC, used from a tablet). Each add-on packages one app so it opens from HA's sidebar (Ingress).

**This repo only packages the apps; it never modifies them.** If an add-on needs something from an app, write it down and ask: the change is made in the app's own repo and conversation. Never copy an app's code into this repo.

## Layout

```
repository.yaml          # repo name, url, maintainer
README.md                # English, generic: table with one row per add-on
<addon>/
  config.yaml            # name, version, slug, arch, ingress, ingress_port, ports, map
  Dockerfile
  run.sh                 # only if needed
  icon.png, logo.png
  DOCS.md                # shown on HA's add-on page (Spanish)
  CHANGELOG.md
```

## How an add-on gets its app's code

The app lives in its own **public** GitHub repo. The add-on's `Dockerfile` downloads it at build time with `ADD <repo>/archive/<ref>.tar.gz` (see `space-race/Dockerfile`). `ADD` re-downloads on every build, so a rebuild picks up the app's latest version. A private app repo would need another approach: ask first.

## Adding a new add-on

1. Read the app's own `CLAUDE.md` and `Dockerfile` (path in `CLAUDE.local.md`); reuse its steps.
2. Create `<addon>/` with the files above, starting from `space-race/` as a template.
3. Add a row to the table in `README.md`.
4. Test it for real: install it in HA and open it on the tablet.

## Gotchas

- **HA only offers an update when `version` in `config.yaml` changes.** Any change to an add-on: bump `version` and add an entry to its `CHANGELOG.md`.
- **Ingress serves the app under `/api/hassio_ingress/<token>/`**: the app must use only relative URLs (and relative redirects).
- **Non-admin users can't open Ingress panels.** For them, also expose a port (`ports:`; Space Race uses 8100) and show it with a "Webpage" dashboard card.
- **Browsers block sound until the first tap**: say so in `DOCS.md` if the app plays audio.
- **Private files (photos, personal config) never go to any repo.** They're copied by hand to HA's `share` folder over Samba; the add-on maps it with `map: [{type: share, read_only: true}]` and the app reads the path from an env var. The steps go in `DOCS.md` (see Space Race's avatars).
- **arch**: `amd64` (the mini PC). Check that the app's dependencies have wheels for it.
- **Languages**: `README.md` in English and generic; `DOCS.md` in Spanish; code, comments and commits in English.
