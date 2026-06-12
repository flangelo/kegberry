# Kegberry Changelog

Join the [kegberry-announce](https://groups.google.com/forum/#!forum/kegberry-announce)
mailing list to be informed of new releases.

## 3.0.0-flangelo1 (2026-06-12)

Complete rewrite of the kegberry deployment for modern Raspberry Pi OS.

**Docker Compose stack** (`docker-compose.yml`):
- New full stack: `kegbot` (Daphne ASGI), `kegnet-listener`, `workers`, `nginx`, `mysql` (MariaDB 10.11), `redis` (Alpine), `pycore`, and `kegboard`.
- All kegbot images pulled from GHCR (`ghcr.io/flangelo/kegbot-server`, `ghcr.io/flangelo/kegbot-pycore`).
- Redis uses the `redis:7.2-alpine` slim image to reduce memory footprint.
- Secrets and kegboard device path injected via `.env` (not baked into compose file).
- kegbot health check gates dependent service startup.
- kegboard waits for Arduino USB device before starting the serial daemon.

**Installer** (`install.sh`):
- Rewritten from scratch. Single-command install: `curl -sSL .../install.sh | bash`.
- Auto-installs Docker Engine, Chromium, and curl if missing.
- Clones the kegberry repo if not already present; updates it if it is.
- Auto-generates `.env` with random secret key and API key.
- Auto-detects Arduino kegboard by USB serial ID (`/dev/serial/by-id/`).
- Pulls pre-built images from GHCR — no local build step required.
- Installs and enables the kiosk systemd service.

**Kiosk service** (`kegbot-kiosk.service`):
- New systemd service that runs Chromium in fullscreen kiosk mode.
- Waits for the kegbot web UI to be reachable before launching.
- Opens `/fullscreen-realtime/` for live pour updates via WebSocket.
- Wipes Chromium's temp profile on each start to prevent crash-restore prompts.

**Nginx** (`nginx.conf`):
- Reverse proxy routing HTTP and WebSocket (`/ws/`) traffic to the kegbot container.
- Serves `/media/` files directly from the host volume.
- Uses Docker's internal DNS resolver for reliable upstream re-resolution after container restarts.


## 2.1.1 (2015-02-03)

- Fixed supervisor.conf


## 2.1.0 (2015-01-27)

- Upgraded `kegbot-server` to version 1.2.3


## 2.0.0 (2014-11-12)

- Overhauled installer script, added new `kegberry` command.
- Servers now run as `kegbot`, no longer run as `pi` user.
- Installs into virtualenv.


## 1.0.3 (2014-07-25)

- Bugfix: Don't prompt for MySQL password during timezone install.


## 1.0.2 (2014-04-23)

- Updates for latest `kegbot-server` commands.
- Installer configures MySQL timezone table.
- Various bugfixes.


## 1.0.1 (2014-02-13)

- Kegberry now includes [kegbot-pycore](https://github.com/Kegbot/kegbot-pycore),
  for optional flow monitoring.
- Various bugfixes.


## 1.0.0 (2014-01-28)

- Added automated installer script.


## 0.0.1 (2013-07-03)

- Initial distribution.
