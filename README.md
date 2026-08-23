# Nest

**Smart Home Bridge** — Links pet behavior to IoT devices — lights dim when the pet sleeps, a lamp warms on hungry.

Part of the [ComputerPets](https://github.com/RicheyWorks/computerpets) ecosystem. Index: [computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem).

> Status: **design scaffold**. This repository ships the contract, README, and layout so implementation can start without renaming the organ later.

## Why it exists

Rui sleeps, the room follows. Nest is opt-in and local-first. No vendor cloud required if you already run MQTT.

The flagship overlay already puts a living sticker on the real desktop (Rui first, 210 kinds). Nest does not replace that. It is one organ.

## Stack

TypeScript · MQTT · Home Assistant discovery · optional Hue / Matter bridge

GroupId / namespace: `com.enterprisepet.nest`  
Default listen: `1883 / 8123`

## Talks to

- computerpets desktop vitals
- computerpets-wallpaper
- computerpets-telemetry (anonymous pulses only)

## Contract

### Data

`Home(id, mqttUrl) · Binding(petId, entityId) · Scene(sleepDim, hungryWarm)`

### Surface

- MQTT computerpets/{petId}/state — sleep|hungry|play
- HA discovery: binary_sensor.pet_asleep, light.pet_den
- POST /v1/pair — local token for this home

### Failure doctrine

Broker down → overlay unaffected. Wrong room scene → one-click disable in tray. Never drive locks or cameras.

## Layout

```
computerpets-nest/
  README.md           this file
  LICENSE             MIT
  docs/CONTRACT.md    the same contract, frozen for implementers
  src/                implementation lands here
```

## Run (Windows)

PowerShell, from this folder, after the flagship helpers (Git, Node LTS 22+, JDK 21 as needed):

```powershell
cd bridge; npm install; npm run start
```

You do not need this service to meet Rui. The [flagship start-here](https://github.com/RicheyWorks/computerpets/blob/main/docs/START-HERE.md) is still the first pet.

## Ecosystem

| Organ | Repo |
| --- | --- |
| Flagship desktop + Spring | [RicheyWorks/computerpets](https://github.com/RicheyWorks/computerpets) |
| This organ | [RicheyWorks/computerpets-nest](https://github.com/RicheyWorks/computerpets-nest) |
| Full map | [RicheyWorks/computerpets-ecosystem](https://github.com/RicheyWorks/computerpets-ecosystem) |

## License

MIT. See [LICENSE](LICENSE).

---

*Two hundred ten living kinds. Keep them so a line does not go quiet.*
