# Android Build Container

Docker containers pre-configured for building AOSP/LineageOS ROMs.

## Profiles

| Profile  | Base             | Use case |
|----------|------------------|----------|
| `archlinux` | Arch Linux    | bleeding-edge toolchains |
| `focal`  | Ubuntu 20.04     | Legacy Kernel (<=4.4) |
| `noble`  | Ubuntu 24.04     | AOSP, LineageOS 21+ |

## Usage

```bash
# Build and start a container
docker compose --profile focal build

# Interactive shell
docker compose --profile focal run --rm focal bash

# Stop and remove
docker compose --profile focal down
```

Replace `focal` with `noble` or `archlinux` as needed.

## Volume

A persistent `buildvol` is mounted at `/root` in each container. Source trees and build outputs survive container restarts.
