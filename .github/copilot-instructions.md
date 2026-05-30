# Copilot instructions — GPU-model-monitor-MQTT

> Canonical standards live in the `dev-standards` repo on SOUNDWAVE/Gitea.
> Read by Copilot chat **and** inline suggestions.

## What this repo is

A standalone **GPU monitor that publishes stats to MQTT** (shell + Python,
Dockerised), with a small HTML stats view. Integrates with Home Assistant via
**MQTT discovery** — it is **not** itself an HA custom component.

## Repo shape

- `monitor_gpu_mqtt.sh`, `monitor_gpu.sh`, `configure_mqtt.sh`, `setup.sh` — shell.
- `mqtt_publisher.py`, `enrich_processes.py`, `server.py` — Python.
- `gpu-stats.html` — stats view.
- `Dockerfile`, `docker-compose.yml`; docs (`FEATURES.md`, `MQTT_PROCESS_INFO.md`,
  `README_MQTT.md`).

## Conventions

- MQTT bridge, not an HA integration: no `manifest.json`/`hassfest`/HACS.
- Integrates with HA via **MQTT discovery** — keep discovery topics/structure
  stable so HA entities don't break.
- Config via the `configure_mqtt.sh` / env path — never commit broker creds.

## Never

- Don't commit MQTT credentials.
