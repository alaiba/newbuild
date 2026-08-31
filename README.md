# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

> **For ChatGPT Work / fresh-agent sessions: start with [`WORK.md`](WORK.md).** It defines source-of-truth precedence, exact SKUs, anti-substitution rules and the current procurement objective.

## Purpose

Greenfield self-built workstation optimized primarily for very heavy Java/Android development, WSL2/containers/local services and occasional VMs, with gaming secondary and cloud AI acceptable where it makes more sense than local hardware.

Design philosophy: **stability first, utility per leu second, speculation last**.

## Current architecture

| Component | Current configuration |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24), DDR5-5600, non-ECC, 1DPC** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** |
| Case airflow | **2× included 140 mm PWM**, front intake + rear exhaust; no extra fans initially |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` |
| Storage expansion | `M.2_2` + `M.2_3` free; reuse healthy existing SATA drives for cold/bulk data |
| Storage RAID/cache/tiering | **None** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable |
| UPS | **None initially** |
| Dedicated surge protector | **None required** |
| Host OS | **Windows 11 Pro x64** |
| Windows license | **Retail/FPP USB English `HAV-00163`** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Key architecture choices

- **48 GB / 2×24 GB / 1DPC** is the selected RAM purchase. It preserves the preferred two-DIMM DDR5-5600 path while avoiding the disproportionate current cost of larger kits.
- RAM capacity is treated as a concurrency limit, not an intrinsic CPU-performance lever: if the working set fits, larger two-DIMM capacities should not materially accelerate the CPU.
- If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit; **do not add a second pair** as the planned upgrade path.
- ECC is not used.
- `M.2_1` hosts the selected **2 TB Crucial T710 Gen5 primary SSD**. `M.2_2` and `M.2_3` remain free for later expansion.
- No separate system/work SSD split, SSD cache layer or automatic tiering is required initially.
- **Phantom Spirit 120 + Pure Base 501** is the final cooling/chassis combination.
- 1 GbE is sufficient; the board's 2.5 GbE is already more than required.
- No multi-GPU/x8+x8 requirement; retire the RTX 3060 if a future GPU replacement occurs.
- **Pure Power 13 M 850W** is selected; 1000–1200 W remains unnecessary.
- No UPS and no dedicated surge protector are purchased initially.

## Procurement position — 2026-08-31

Architecture and exact component selection are closed.

The current task is **same-day procurement verification**:

- confirm exact SKUs;
- confirm new-retail condition and warranty path;
- refresh stock/lead time and delivered prices;
- consolidate to at most three providers overall / two hardware providers where value allows.

The exact selected motherboard is **B650E-E `90MB1LT0-M0EAY0`**; do not confuse it with the separately sold B650-E `90MB1GT0-M0EAY0`.

The exact selected RAM is **Crucial Pro `CP2K24G56C46U5` = 48 GB as 2×24 GB**; do not confuse it with a single 48 GB module.

Reference complete-build pricing from the last pass was roughly **~11.0–11.3k lei before shipping**, depending mainly on the RAM supplier. Treat this only as a snapshot and refresh live prices before payment.

## Repository structure

- [`WORK.md`](WORK.md) — **mandatory fresh-session / ChatGPT Work entrypoint**
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened/superseded decisions
- [`docs/requirements.md`](docs/requirements.md) — workload and governing requirements
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement policy/state
- [`docs/final-order-plan-2026-08-31.md`](docs/final-order-plan-2026-08-31.md) — current priced-basket framework
- [`docs/checkout-checklist.md`](docs/checkout-checklist.md) — exact-SKU verification workflow
- [`docs/ram-capacity-sensitivity-2026-08-31.md`](docs/ram-capacity-sensitivity-2026-08-31.md) — resolved RAM analysis; final decision is 48 GB
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/constraints
- [`docs/components/`](docs/components/) — component deep dives

Historical/date-stamped snapshots may contain superseded architectures. Follow the precedence rules in `WORK.md` whenever files disagree.

## Current stage

**Purchase-ready architecture.** No component-selection work remains; perform live checkout verification, then move to assembly and commissioning.
