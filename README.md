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
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24), DDR5-5600 CL46-class, 1.1 V, non-ECC, 1DPC** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** |
| Case airflow | **2× included 140 mm PWM**, front intake + rear exhaust; no extra fans initially |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` |
| Storage expansion | `M.2_2` + `M.2_3` free; reuse healthy existing SATA drives for cold/bulk data |
| Storage RAID/cache/tiering | **None** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 |
| UPS | **None initially** |
| Dedicated surge protector | **None required** |
| GPU | Existing **RTX 3060 12 GB**, reused for as long as useful/reliable |
| Host OS | **Windows 11 Pro x64** |
| Windows license | **Retail/FPP USB English `HAV-00163`** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** |

## Key architecture choices

- **48 GB / 2×24 GB / 1DPC** is the selected RAM purchase. It preserves the full two-DIMM DDR5-5600 path while avoiding the disproportionate current cost of 64/128 GB kits.
- RAM capacity is treated as a concurrency limit, not an intrinsic CPU-performance lever: if the working set fits, larger two-DIMM capacities should not materially accelerate the CPU.
- If 48 GB later proves insufficient, replace the pair with a larger two-DIMM kit; **do not add a second pair** and move to four DIMMs.
- ECC is not used.
- `M.2_1` hosts the selected 2 TB Crucial T710 Gen5 primary SSD. `M.2_2` and `M.2_3` remain free for later expansion.
- No separate system/work SSD split, SSD cache layer or automatic tiering is required initially.
- 1 GbE is sufficient; the board's 2.5 GbE is already more than required.
- No multi-GPU/x8+x8 requirement; retire the RTX 3060 if a future GPU replacement occurs.
- Pure Power 13 M 850W is selected; 1000–1200 W remains unnecessary.
- No UPS and no dedicated surge protector are purchased initially.

## Procurement position — 2026-08-31

The 48 GB Crucial Pro kit currently surfaces in Romania from approximately **2,899 lei**. Re-run same-day supplier consolidation before payment because RAM pricing remains volatile.

The exact selected motherboard is **B650E-E `90MB1LT0-M0EAY0`**; do not confuse it with the separately sold B650-E `90MB1GT0-M0EAY0`.

See:

- [`docs/final-order-plan-2026-08-31.md`](docs/final-order-plan-2026-08-31.md)
- [`docs/ram-capacity-sensitivity-2026-08-31.md`](docs/ram-capacity-sensitivity-2026-08-31.md)

## Current open work

No architecture decision remains open. Before payment, perform a same-day stock/price/provider refresh for the selected 48 GB kit and exact motherboard.

## Repository structure

- [`docs/requirements.md`](docs/requirements.md)
- [`docs/decisions.md`](docs/decisions.md)
- [`docs/final-build.md`](docs/final-build.md)
- [`docs/procurement-plan-2026-08-31.md`](docs/procurement-plan-2026-08-31.md)
- [`docs/final-order-plan-2026-08-31.md`](docs/final-order-plan-2026-08-31.md)
- [`docs/ram-capacity-sensitivity-2026-08-31.md`](docs/ram-capacity-sensitivity-2026-08-31.md)
- [`docs/compatibility.md`](docs/compatibility.md)
- [`docs/components/`](docs/components/)

## Current stage

**Purchase-ready architecture.** RAM is now closed at **48 GB / 2×24 GB**; only same-day procurement verification remains.
