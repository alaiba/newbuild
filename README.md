# New PC Build

Research and decision record for a new long-lived workstation PC.

## Fixed inputs

The build is greenfield. **No component has been selected except the GPU that will be reused initially.**

- Existing GPU: **NVIDIA GeForce RTX 3060 12 GB**
- Programming and software development are the primary workload
- Docker and WSL2
- Virtual machines
- Occasional Genshin Impact
- Possible local AI experimentation
- Target useful lifespan: 7–10 years
- Budget ceiling: 20,000 lei
- Location: Iași, Romania
- Self-assembled

## Component status

| Component | Status | Notes |
|---|---|---|
| CPU/platform | Open | No vendor, socket, chipset or CPU selected |
| Motherboard | Open | MSI MAG X870 TOMAHAWK WIFI is only an initial comparison candidate, not a decision |
| Memory | Open | Capacity, topology, speed and ECC/non-ECC are all to be evaluated |
| CPU cooler | Open | Air vs liquid and exact model are undecided |
| Storage | Open | Capacity, number of drives, interface and exact models are undecided |
| PSU | Open | Wattage, platform and exact model are undecided |
| Case | Open | Exact case and airflow design are undecided |
| Case fans | Open | Depends on case and thermal design |
| GPU | **Selected / existing** | Reuse NVIDIA GeForce RTX 3060 12 GB initially |
| UPS | Open | Topology, capacity and exact model are undecided |
| OS | Open | To be evaluated as part of the workstation design |

Previously discussed parts such as the Ryzen 9 9950X, MSI MAG X870 TOMAHAWK WIFI, 128 GB 2×64 GB DDR5, Noctua NH-D15 G2, dual NVMe drives and 1000 W ATX 3.1 PSUs are **research candidates or hypotheses only**. They must earn their place in the final build through the component reviews.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — fixed workload, constraints and evaluation criteria
- [`docs/decisions.md`](docs/decisions.md) — closed decisions only
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component compatibility and topology constraints as they emerge
- [`docs/final-build.md`](docs/final-build.md) — final bill of materials when decisions are complete
- [`docs/components/`](docs/components/) — one technical dossier per component

## Research approach

Each component should be evaluated from first principles against the workload and longevity goals. Existing candidates provide useful comparison points but are not privileged defaults.

The order of investigation may change when one decision constrains another. Motherboard/platform and memory are natural early topics because they are tightly coupled, but even the CPU platform itself remains open.
