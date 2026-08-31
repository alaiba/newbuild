# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

## Purpose

Greenfield self-built workstation optimized primarily for:

- very heavy Java development across very large codebases;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- Docker/WSL2, local services/databases and occasional VMs;
- occasional gaming as a secondary workload;
- local AI only when it is concretely useful; cloud AI/training remains an acceptable alternative.

The design philosophy is **stability first, utility per leu second, speculation last**. Do not spend merely because the planning budget has headroom.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **Reopened for optimization** from a broad AM5 set; Creator-class features no longer privileged |
| RAM | **128 GB final from day one, 2×64 GB DDR5 UDIMM / 1DPC**; exact kit/ECC verdict open |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset |
| System storage | **~1 TB**, NVMe preferred but SATA acceptable if topology/value warrants it |
| Active-work SSD | **1 TB sufficient; 2 TB if price/value is attractive**, Gen4 TLC preferred; **CPU-direct M.2 x4 required** |
| Bulk/cold storage | Add only when needed via spare M.2, SATA SSD/HDD or external/NAS |
| Storage RAID | **None** |
| PSU | **Premium 750 W / 850 W ATX 3.1**, exact model open |
| UPS | **None initially** |
| Point-of-use power protection | Reputable surge-protected plug/power strip |
| Case | **Fractal North XL Mesh `FD-C-NOR1X-01`**, selected for now but worth one final value/size check |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable |
| Host OS | **Windows 11 Pro x64**, initial 25H2 GA |
| Windows license | **Retail/FPP USB English `HAV-00163`**, current target PROstore |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Key simplifications

- No planned 256 GB/four-DIMM memory endpoint.
- No 4 TB performance SSD requirement.
- Only **one CPU-direct M.2 x4** connection is mandatory; a second M.2 is desirable, not required.
- 1 GbE is sufficient; do not pay for 5/10 GbE.
- No multi-GPU/x8+x8 requirement; retire the 3060 when/if a future replacement occurs.
- Do not pre-size the platform for a hypothetical 500–600 W future GPU.
- 1200 W PSU selection is superseded; optimize premium **750 W vs 850 W**.
- Large UPS selection is superseded; no UPS initially.
- Extreme-overclocking VRM capability has no value for stock/conservative 9950X3D operation.

## Current open work

1. Optional final **case size/value check**.
2. Re-optimize the **motherboard** against the simplified requirements.
3. Select exact **2×64 GB RAM** and ECC/non-ECC verdict.
4. Select exact system and active-work storage.
5. Select exact premium **750/850 W PSU**.
6. Refresh prices/providers and final total.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload and governing requirements
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened decisions
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement state
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component constraints
- [`docs/components/`](docs/components/) — component deep dives

## Current stage

**The build has been aggressively de-speculated. Motherboard optimization can now start from the actual workload rather than from hypothetical 256 GB, 10 GbE, multi-GPU, multiple-Gen5-M.2 or 600 W future-GPU requirements.**
