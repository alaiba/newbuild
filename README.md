# New PC Build

Research and decision record for a new long-lived workstation PC.

## Primary goals

- Programming and software development
- Docker and WSL2
- Virtual machines
- Occasional Genshin Impact
- Possible entry-level local AI experimentation
- Target useful lifespan: 7–10 years
- Budget ceiling: 20,000 lei
- Location: Iași, Romania
- Self-assembled
- Reuse the existing NVIDIA GeForce RTX 3060 12 GB initially

## Current target

| Component | Current target | Status |
|---|---|---|
| CPU | AMD Ryzen 9 9950X | Candidate |
| Motherboard | MSI MAG X870 TOMAHAWK WIFI | Under review |
| Memory | 128 GB DDR5, 2×64 GB, nominal target 5600 MT/s | Depends on motherboard |
| CPU cooler | Noctua NH-D15 G2 | Candidate |
| System SSD | 2 TB PCIe 4.0 TLC NVMe | Model TBD |
| Work / VM SSD | 4 TB PCIe 4.0 TLC NVMe | Model TBD |
| PSU | Seasonic Vertex GX-1000 or Corsair RM1000x ATX 3.1 | Candidate |
| Case | Fractal Meshify 2 or be quiet! Silent Base 802 | Candidate |
| GPU | Existing NVIDIA GeForce RTX 3060 12 GB | Reuse |
| UPS | 1000–1500 VA line-interactive class | Specification TBD |
| OS | Windows 11 Pro + WSL2 | TBD |

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload, constraints and priorities
- [`docs/decisions.md`](docs/decisions.md) — decision log
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component compatibility and topology
- [`docs/final-build.md`](docs/final-build.md) — final bill of materials when decisions are complete
- [`docs/components/`](docs/components/) — one technical dossier per component

## Review order

1. Motherboard
2. Memory
3. CPU
4. Cooling
5. Storage
6. PSU
7. Case and airflow
8. GPU
9. UPS

The motherboard and memory are deliberately reviewed first because they form the most compatibility-sensitive part of the platform, particularly with a 128 GB 2×64 GB configuration.
