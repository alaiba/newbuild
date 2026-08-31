# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

## Purpose

Greenfield self-built workstation optimized primarily for:

- very heavy Java development across very large codebases;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- Docker/WSL2, local services/databases and occasional VMs;
- occasional gaming as a secondary workload;
- local AI only when concretely useful; cloud AI/training remains an acceptable alternative.

The design philosophy is **stability first, utility per leu second, speculation last**.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **Reopened for optimization** from a broad AM5 set; **ATX or smaller** |
| RAM | **128 GB final from day one, 2×64 GB DDR5 UDIMM / 1DPC**; exact kit/ECC verdict open |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** |
| Case airflow | **2× included 140 mm PWM**, front intake + rear exhaust; no extra fans initially |
| System storage | **~1 TB**, NVMe preferred but SATA acceptable if topology/value warrants it |
| Active-work SSD | **1 TB sufficient; 2 TB if price/value is attractive**, Gen4 TLC preferred; **CPU-direct M.2 x4 required** |
| Bulk/cold storage | Add only when needed via spare M.2, SATA SSD/HDD or external/NAS |
| Storage RAID | **None** |
| PSU | **Premium 750 W / 850 W ATX 3.1**, exact model open |
| UPS | **None initially** |
| Point-of-use power protection | Reputable surge-protected plug/power strip |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable |
| Host OS | **Windows 11 Pro x64**, initial 25H2 GA |
| Windows license | **Retail/FPP USB English `HAV-00163`**, current target PROstore |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Key simplifications

- No planned 256 GB/four-DIMM memory endpoint.
- **Phantom Spirit 120 + Pure Base 501** replaces NH-D15 G2 + North XL.
- No dedicated extra case-fan purchase initially.
- No 4 TB performance SSD requirement.
- Only **one CPU-direct M.2 x4** connection is mandatory; a second M.2 is desirable, not required.
- 1 GbE is sufficient; do not pay for 5/10 GbE.
- No multi-GPU/x8+x8 requirement; retire the 3060 when/if a future replacement occurs.
- Do not pre-size the platform for a hypothetical 500–600 W future GPU.
- 1200 W PSU selection is superseded; optimize premium **750 W vs 850 W**.
- Large UPS selection is superseded; no UPS initially.
- Extreme-overclocking VRM capability has no value for stock/conservative 9950X3D operation.

## Current open work

1. Re-optimize the **motherboard** against the simplified requirements and selected ATX case.
2. Select exact **2×64 GB RAM** and ECC/non-ECC verdict.
3. Select exact system and active-work storage.
4. Select exact premium **750/850 W PSU**.
5. Select exact plug-in surge protector.
6. Refresh prices/providers and final total.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload and governing requirements
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened decisions
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement state
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component constraints
- [`docs/components/`](docs/components/) — component deep dives

## Current stage

**Case and CPU cooling are now closed. The next coupled optimization is motherboard + exact 2×64 GB memory.**
