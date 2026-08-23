# Nest contract

Do not implement against folklore. Implement against this file.

## Identity

- Product: **Nest**
- Repo: `computerpets-nest`
- Category: Integrations
- Idea: Smart Home Bridge
- Port / surface: `1883 / 8123`

## Must

- Stay canon with 210 species. No illegal hybrids. No swapped voices.
- Treat the desktop overlay as the main quest. This organ is optional until wired.
- Fail soft: the overlay keeps walking if this service is down, unless this *is* the overlay.
- No PII in public artifacts (Steam id, wallet, home path, webcam frames).

## Data

Home(id, mqttUrl) · Binding(petId, entityId) · Scene(sleepDim, hungryWarm)

## Surface

- MQTT computerpets/{petId}/state — sleep|hungry|play
- HA discovery: binary_sensor.pet_asleep, light.pet_den
- POST /v1/pair — local token for this home

## Neighbors

- computerpets desktop vitals
- computerpets-wallpaper
- computerpets-telemetry (anonymous pulses only)

## Failure doctrine

Broker down → overlay unaffected. Wrong room scene → one-click disable in tray. Never drive locks or cameras.

## Stack

TypeScript · MQTT · Home Assistant discovery · optional Hue / Matter bridge
