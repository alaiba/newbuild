# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

## Purpose

Greenfield self-built workstation optimized primarily for:

- very heavy Java development across very large codebases;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- Docker/WSL2, local services/databases and occasional VMs;
- occasional gaming as a secondary workload;
- a future single very high-performance/high-VRAM GPU for local AI.

The design philosophy is **stability first**: conservative operation, mature firmware, thermal/electrical margin, reliability, serviceability and long ownership are preferred over short-lived benchmark gains or aggressive tuning.

Planning level is approximately **30,000 lei**, not a target and not a hard cap. The current initial build remains materially below it.

## Selected initial build

| Component | Selected configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** |
| Phase-1 RAM | **64 GB (2×32) Crucial `CT2K32G56C46U5`, DDR5-5600 CL46, 1.1 V** |
| Long-term RAM | **256 GB target**, expected 4×64 GB; exact modules/ECC verdict deferred |
| CPU cooler | **Noctua NH-D15 G2 standard `CPNTD15G2`**, 7 mm AM5 offset |
| System SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`**, installed in ProArt `M.2_3` |
| Future work SSD | 4 TB-or-larger NVMe later; reserve `M.2_1` |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** |
| Case | **Fractal Design North XL Mesh Charcoal Black `FD-C-NOR1X-01`** |
| Airflow | 3× included 140 mm front intake + 1× **Noctua NF-A14x25 G2 PWM** rear exhaust |
| GPU | Existing **RTX 3060 12 GB**, reused initially |
| UPS | **CyberPower CP1600EPFCLCD** |
| Host OS | **Windows 11 Pro x64**, initial install 25H2 GA |
| Windows license | **Retail/FPP USB English `HAV-00163`** — required purchase |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

Representative current complete initial order is approximately **18.9–19.3k lei before shipping**, including Windows Retail/FPP and excluding the reused RTX 3060.

## Important operating policies

- Ryzen CPU remains stock/conservative; no uncapped-PBO policy.
- RAM starts at Auto/JEDEC and receives extended stability testing before any optional profile tuning.
- Eventual 256 GB memory is a new matched-set purchase; prefer ECC UDIMM only if exact modules, four-DIMM stability and OS-visible ECC reporting are credible.
- Samsung 990 PRO is the permanent system/tools drive; no RAID.
- Preserve `M.2_1` for the future work/VM/container SSD and avoid `M.2_2` unless its GPU-lane trade-off is deliberately accepted.
- Keep the initial case airflow simple: front intake + rear exhaust; add top/side fans only if measurements justify them.
- UPS is sized for the initial RTX 3060 system and must be reassessed with a materially higher-power future GPU.
- Windows baseline is production/GA only; no Insider baseline.
- Linux-native high-I/O work belongs inside the WSL filesystem rather than `/mnt/c`.
- BitLocker is enabled only after the initial BIOS/firmware/driver baseline is stable.

## Procurement policy

- **PC Garage and Altex are co-preferred Romanian retailers**.
- **eMAG is also acceptable**.
- Other established Romanian/EU sellers are acceptable when preferred sellers are unavailable, materially more expensive or ambiguous about the exact SKU/revision.
- Exact SKU/revision, invoice/warranty path and product condition outrank retailer loyalty.
- Do not substitute similar-looking SKUs without reopening the relevant purchase gate.

The current exact order split, price controls and rejection gates are in [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md).

## Still intentionally deferred

- exact eventual 256 GB 4×64 GB memory set and ECC/non-ECC decision;
- validation of operational system-level ECC reporting if ECC is used;
- exact future 4 TB+ work SSD;
- future high-VRAM GPU;
- UPS enlargement if the future GPU/load requires it;
- exact container runtime if licensing/workflow makes the choice material.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload, constraints and evaluation criteria
- [`docs/decisions.md`](docs/decisions.md) — closed decisions and reopen conditions
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth BOM and bring-up baseline
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — purchase-ready order plan, exact SKUs, seller controls and acceptance gates
- [`docs/purchase-review-2026-08-31.md`](docs/purchase-review-2026-08-31.md) — dated cost snapshot
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/compatibility constraints
- [`docs/cost-value-matrix.md`](docs/cost-value-matrix.md) — build-level cost/value reasoning
- [`docs/components/`](docs/components/) — component deep dives and evidence

## Current stage

**Component selection is complete for the initial build. Current work is procurement execution, followed by assembly, firmware setup and burn-in/validation.**
