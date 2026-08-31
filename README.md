# New PC Build

Research, decisions and procurement record for a new long-lived professional workstation PC.

> **For ChatGPT Work / fresh-agent sessions: start with [`WORK.md`](WORK.md).** It defines source-of-truth precedence, exact SKUs, anti-substitution rules and the current procurement objective.

## Purpose

Greenfield self-built workstation optimized primarily for very heavy Java/Android development, WSL2/containers/local services and occasional VMs, with gaming secondary and cloud AI acceptable where it makes more sense than local hardware.

Design philosophy: **stability first, utility per leu second, speculation last**.

## Current architecture and procurement state

| Component | Current configuration | State |
|---|---|---|
| CPU | **AMD Ryzen 9 9950X3D**, Box/WOF `100-100000719WOF` | **Purchased 2026-09-01 — EvoMAG** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Purchased 2026-09-01 — EvoMAG; physical SKU verification pending** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24), DDR5-5600, non-ECC, 1DPC** | **Not yet purchased** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | **Not yet purchased** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Not yet purchased** |
| Case airflow | **2× included 140 mm PWM**, front intake + rear exhaust; no extra fans initially | Selected |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Purchased 2026-09-01 — EvoMAG** |
| Storage expansion | `M.2_2` + `M.2_3` free; reuse healthy existing SATA drives for cold/bulk data | Selected |
| Storage RAID/cache/tiering | **None** | Selected |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Purchased 2026-09-01 — EvoMAG** |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable | Already owned |
| UPS | **None initially** | No purchase planned |
| Dedicated surge protector | **None required** | No purchase planned |
| Host OS | **Windows 11 Pro x64** | Selected; license already available |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | Selected |

## First executed order — 2026-09-01

EvoMAG order:

- Ryzen 9 9950X3D Box — **3,349.99 lei**;
- ASUS TUF GAMING B650E-E WIFI — **785.99 lei**;
- Crucial T710 2 TB — **1,699.99 lei**;
- be quiet! Pure Power 13 M 850W — **683.99 lei**;
- hardware subtotal — **6,519.96 lei**;
- courier — **11.99 lei**;
- **total — 6,531.95 lei including VAT**.

These four items are now committed purchases. Their next step is arrival verification, not further price shopping.

See [`docs/purchases-2026-09-01.md`](docs/purchases-2026-09-01.md).

## Key architecture choices

- **48 GB / 2×24 GB / 1DPC** is the selected RAM purchase. It preserves the preferred two-DIMM DDR5-5600 path while avoiding the disproportionate current cost of larger kits.
- RAM capacity is treated as a concurrency limit, not an intrinsic CPU-performance lever: if the working set fits, larger two-DIMM capacities should not materially accelerate the CPU.
- If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit; **do not add a second pair** as the planned upgrade path.
- ECC is not used.
- `M.2_1` hosts the purchased **2 TB Crucial T710 Gen5 primary SSD**. `M.2_2` and `M.2_3` remain free for later expansion.
- No separate system/work SSD split, SSD cache layer or automatic tiering is required initially.
- **Phantom Spirit 120 + Pure Base 501** remains the final cooling/chassis combination; both still need to be sourced.
- 1 GbE is sufficient; the board's 2.5 GbE is already more than required.
- No multi-GPU/x8+x8 requirement; retire the RTX 3060 if a future GPU replacement occurs.
- **Pure Power 13 M 850W** is purchased; 1000–1200 W remains unnecessary.
- No UPS and no dedicated surge protector are purchased initially.
- Windows 11 Pro remains the selected host OS, but the license is **already available and excluded from procurement**.

## Procurement position — 2026-09-01

Architecture and exact component selection are closed. Procurement is **partially complete**.

Already purchased:

- CPU;
- motherboard;
- primary SSD;
- PSU.

Already available outside this hardware order:

- Windows 11 Pro license.

Still to purchase:

- exact Crucial Pro `CP2K24G56C46U5` RAM;
- exact Thermalright Phantom Spirit 120 standard cooler;
- exact be quiet! Pure Base 501 Airflow Black `BG074` case.

The exact selected motherboard remains **B650E-E `90MB1LT0-M0EAY0`**; verify that manufacturer code on the physical box before installation because the retailer order text records the model name but not a trustworthy full SKU.

## Repository structure

- [`WORK.md`](WORK.md) — **mandatory fresh-session / ChatGPT Work entrypoint**
- [`docs/final-build.md`](docs/final-build.md) — current source-of-truth architecture and purchase state
- [`docs/decisions.md`](docs/decisions.md) — closed/reopened/superseded decisions
- [`docs/requirements.md`](docs/requirements.md) — workload and governing requirements
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md) — procurement policy/state
- [`docs/final-order-plan-2026-08-31.md`](docs/final-order-plan-2026-08-31.md) — executed/remaining order framework
- [`docs/purchases-2026-09-01.md`](docs/purchases-2026-09-01.md) — first executed purchase record
- [`docs/checkout-checklist.md`](docs/checkout-checklist.md) — exact-SKU purchase and arrival verification workflow
- [`docs/ram-capacity-sensitivity-2026-08-31.md`](docs/ram-capacity-sensitivity-2026-08-31.md) — resolved RAM analysis; final decision is 48 GB
- [`docs/compatibility.md`](docs/compatibility.md) — cross-component topology/constraints
- [`docs/components/`](docs/components/) — component deep dives

Historical/date-stamped snapshots may contain superseded architectures. Follow the precedence rules in `WORK.md` whenever files disagree.

## Current stage

**Partial procurement.** Complete sourcing for **RAM, cooler and case**; verify purchased hardware on arrival; then move to assembly and commissioning.
