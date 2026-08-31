# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

## Purpose

Greenfield self-built workstation optimized primarily for very heavy Java/Android development, WSL2/containers/local services and occasional VMs, with gaming secondary and cloud AI acceptable where it makes more sense than local hardware.

Design philosophy: **stability first, utility per leu second, speculation last**.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** |
| RAM | **Crucial `CT2K64G56C46U5` — 128 GB (2×64), DDR5-5600 CL46, 1.1 V, non-ECC, 1DPC** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** |
| Case airflow | **2× included 140 mm PWM**, front intake + rear exhaust; no extra fans initially |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` |
| Storage expansion | `M.2_2` + `M.2_3` free; reuse healthy existing SATA drives for cold/bulk data |
| Storage RAID/cache/tiering | **None** |
| PSU | **Premium 750 W / 850 W ATX 3.1**, exact model open |
| UPS | **None initially** |
| Point-of-use power protection | Reputable surge-protected Schuko plug/power strip, exact model open |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable |
| Host OS | **Windows 11 Pro x64**, initial 25H2 GA |
| Windows license | **Retail/FPP USB English `HAV-00163`**, current target PROstore |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Key architecture choices

- 128 GB is bought once as **2×64 GB / 1DPC**; no temporary RAM and no planned 256 GB/four-DIMM endpoint.
- Exact RAM uses **native JEDEC DDR5-5600 at 1.1 V**; no EXPO/XMP is required.
- ECC is not used because practical 64 GB ECC UDIMM procurement is poor; CPU/board ECC capability remains unused rather than distorting capacity/topology.
- **B650 is sufficient**: the selected B650E-E provides PCIe 5.0 x16 graphics, two CPU-connected M.2 paths, a third chipset Gen4 x4 M.2, BIOS FlashBack, Q-LED, SATA and adequate stock-load power delivery without B850/Creator premiums.
- `M.2_1` hosts the selected **2 TB Crucial T710 Gen5 primary SSD**. `M.2_2` and `M.2_3` remain free for later expansion.
- Current storage use is about **600 GB**; 2 TB is ample foreseeable active-storage headroom. Existing SATA drives remain useful for archives/cold data.
- No separate system/work SSD split, no SSD cache layer and no automatic tiering are required initially.
- **Phantom Spirit 120 + Pure Base 501** replaces NH-D15 G2 + North XL.
- 1 GbE is sufficient; the board's 2.5 GbE is already more than required.
- No multi-GPU/x8+x8 requirement; retire the RTX 3060 if a future GPU replacement occurs.
- Do not pre-size the platform for a hypothetical 500–600 W future GPU.
- 1200 W PSU and large UPS are superseded; optimize **750 W vs 850 W**, with no UPS initially.

## Current open work

1. Select exact premium **750/850 W PSU**.
2. Select exact **plug-in surge protector**.
3. Refresh prices/providers and produce the final order total.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md) — workload and governing requirements
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened decisions
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement state
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component constraints
- [`docs/components/`](docs/components/) — component deep dives

## Current stage

**CPU, motherboard, RAM, cooler, case and primary storage are closed. PSU and point-of-use surge protection are next.**
