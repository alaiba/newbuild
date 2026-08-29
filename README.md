# New PC Build

Research and decision record for a new long-lived workstation PC.

## Fixed inputs and selected direction

This is a greenfield build assembled from scratch.

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5
- **Memory target:** 256 GB initial build target
- **Existing GPU:** NVIDIA GeForce RTX 3060 12 GB, reused initially
- **Primary workload:** very heavy Java development, IntelliJ IDEA, Android Studio, Maven/Gradle builds, large test suites, Docker, WSL2, local services/databases and occasional VMs
- **Secondary workload:** occasional gaming
- **Secondary future objective:** preserve a credible path to a very powerful single high-VRAM GPU for local AI workloads without compromising the primary workstation
- **Longevity objective:** approximately 10 years of useful life, especially if the final cost approaches or exceeds the 30,000 lei planning level
- **Planning budget level:** 30,000 lei; not a hard cap and not a spending target
- **Location:** Iași, Romania
- **Assembly:** self-built

The design philosophy is **stability first**. Prefer mature firmware, conservative memory settings, thermal/electrical headroom, reliable components, serviceability and long-term usefulness over short-lived benchmark gains or extreme tuning.

## Component status

| Component | Status | Notes |
|---|---|---|
| CPU/platform | **Selected** | AMD Ryzen 9 9950X3D on AM5 |
| Motherboard | Open / next decision | Must officially support 256 GB and provide credible high-density-memory stability; ECC and future AI/GPU topology are important evaluation factors |
| Memory | **256 GB target selected** | Exact 4×64 GB or equivalent configuration, data rate and ECC/non-ECC mode remain open |
| CPU cooler | Open | Must support sustained 9950X3D workloads with thermal/acoustic headroom and strong long-term reliability |
| Storage | Open | Capacity, number of drives, interface and exact models remain open; endurance/data integrity matter |
| PSU | Open | Must preserve appropriate headroom for a future very high-power GPU |
| Case | Open | Must support long-term serviceability, airflow and a future large GPU |
| Case fans | Open | Depends on case and thermal design |
| GPU | **Selected / existing** | Reuse RTX 3060 12 GB initially; preserve future single high-VRAM GPU path |
| UPS | Open | Topology, capacity and exact model are undecided |
| OS | Open | To be evaluated as part of the workstation design |

## Key closed decisions

The main closed decisions are recorded in [`docs/decisions.md`](docs/decisions.md).

Current important decisions include:

- Ryzen 9 9950X3D + AM5 selected over Threadripper/workstation alternatives for the best overall balance of professional development performance, interactive use, gaming and total platform cost.
- 256 GB is the initial memory-capacity target; scale back only if current cost or stable AM5 operation makes it disproportionate.
- Only motherboards with manufacturer-documented 256 GB support are eligible.
- ECC UDIMM is a strong reliability preference if a stable 256 GB implementation with meaningful OS-visible error reporting can be established.
- Future local AI is a secondary objective: preserve compatibility with one extremely powerful/high-VRAM GPU; do not overbuild today for serious multi-GPU training.
- 30,000 lei is a planning level, not a hard cap. A build near or above that level must earn the spend through a credible long-term performance/reliability/endurance/serviceability story.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload, constraints, reliability philosophy and evaluation criteria
- [`docs/decisions.md`](docs/decisions.md) — closed decisions only
- [`docs/cost-value-matrix.md`](docs/cost-value-matrix.md) — living build-level matrix for cost, performance, reliability, endurance, expansion and 10-year value
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component compatibility and topology constraints as they emerge
- [`docs/final-build.md`](docs/final-build.md) — final bill of materials as component decisions close
- [`docs/components/`](docs/components/) — one technical dossier per component

## Research approach

Each component is evaluated against the real workload and the intended long ownership horizon. The goal is not the cheapest acceptable build and not the fastest benchmark build.

For every material price premium, determine what it actually buys in:

- relevant workload performance;
- stability and data integrity;
- reliability and endurance;
- acoustics and thermal headroom;
- serviceability;
- expansion capability; and
- expected usefulness over approximately 10 years.

Current next step: **select the motherboard**, with particular emphasis on stable 256 GB operation, ECC implementation, firmware maturity, PCIe/M.2 topology, future high-end GPU support and long-term serviceability.
