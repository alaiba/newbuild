# Build Requirements

## Scope

This is a **new build from scratch** for a long-lived professional workstation.

Current fixed architecture:

- **CPU/platform:** AMD Ryzen 9 9950X3D on AM5;
- **motherboard:** ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`;
- **memory:** Crucial Pro `CP2K24G56C46U5`, **48 GB = 2×24 GB DDR5-5600 / 1DPC / non-ECC**, conservative 1.1 V-class operation;
- **cooler:** Thermalright Phantom Spirit 120 standard;
- **chassis:** be quiet! Pure Base 501 Airflow Black `BG074`;
- **initial airflow:** two included 140 mm PWM fans, front intake + rear exhaust;
- **primary storage:** Crucial T710 2 TB `CT2000T710SSD8`, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` under the motherboard heatsink;
- **storage architecture:** one primary NVMe initially; no separate system/work SSD, SSD cache or automatic tiering;
- **cold/bulk storage:** reuse existing SATA drives where appropriate after health validation;
- **PSU:** be quiet! Pure Power 13 M 850W `BP027EU`, ATX 3.1;
- **GPU:** reuse RTX 3060 12 GB for as long as useful/reliable;
- **host OS:** Windows 11 Pro x64 with WSL2 + Ubuntu 26.04.1 LTS;
- **Windows license:** Retail/FPP English USB `HAV-00163`;
- **UPS:** none initially;
- **dedicated surge protection:** none required initially.

No component-selection decision remains open. Only same-day supplier/price/SKU verification remains before payment.

## Workload priority

### Primary
- very heavy Java development across codebases with millions of lines;
- IntelliJ IDEA and Android Studio;
- Maven/Gradle builds and large test suites;
- multiple JVMs/local services;
- WSL2, containers, Android Emulator, local databases and occasional VMs.

### Secondary
- occasional gaming;
- local AI only when concretely useful; cloud AI/training is acceptable.

## Design philosophy

Target a long useful life where economically sensible, but **do not pre-buy speculative capability**.

Prioritize stability, mature firmware, conservative operation, serviceability, appropriate thermal/electrical margin, memory stability, storage endurance and utility per leu.

## Motherboard requirements — satisfied

Selected: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

Required/accepted characteristics:

- ATX fit in the selected case;
- Ryzen 9 9950X3D / Ryzen 9000 support;
- primary CPU-connected PCIe 5.0 x16 graphics path;
- CPU-connected `M.2_1` PCIe 5.0 x4 for the selected primary SSD;
- CPU-connected `M.2_2` PCIe 4.0 x4 for later expansion;
- chipset-connected `M.2_3` PCIe 4.0 x4 for later expansion;
- sufficient stock/conservative 9950X3D power delivery;
- BIOS FlashBack and Q-LED diagnostics;
- four SATA ports;
- 2.5 GbE, already beyond the actual network requirement.

Explicitly **not requirements**: B850 itself, 5/10 GbE, CPU x8/x8, a secondary PCIe x4 expansion slot, multiple Gen5 M.2 slots, extreme-overclocking capability and provisioning for a hypothetical 500–600 W future GPU.

The second physical x16 slot operates at chipset PCIe 4.0 x1. This is accepted because no high-bandwidth add-in card is currently required.

## Memory requirements — satisfied

Selected: **Crucial Pro `CP2K24G56C46U5`**.

- 48 GB total;
- matched **2×24 GB** DDR5 UDIMM;
- 1DPC, install in A2/B2;
- DDR5-5600;
- conservative 1.1 V-class operation;
- non-ECC;
- low-profile desktop modules.

Operating policy:

- current stable production BIOS;
- Auto/JEDEC first;
- no EXPO/XMP required during initial commissioning;
- extended memory validation before commissioning;
- no voltage/timing tuning merely for benchmark gains.

### Capacity policy

48 GB was selected because current 64/128 GB pricing is disproportionate and larger two-DIMM capacities do not materially improve CPU throughput while the active working set already fits.

The trade-off is **concurrency headroom**, not intrinsic CPU speed.

If real monitoring later shows persistent memory pressure, **replace the pair with a larger matched two-DIMM kit**. Do not add another pair: preserve the preferred AM5 1DPC topology.

### ECC verdict

The CPU/board can support ECC UDIMM, but ECC is not a purchase requirement. Do not use RDIMM; AM5 requires UDIMM.

## Cooling and chassis

Selected:

- Thermalright Phantom Spirit 120 standard;
- be quiet! Pure Base 501 Airflow Black `BG074`;
- only the two included 140 mm PWM case fans initially.

Policy:

- stock/conservative 9950X3D;
- no liquid/pump dependency unless measurements establish a real need;
- no silent substitution of Phantom Spirit SE/EVO;
- add another front intake only if closed-case measurements justify it.

## Storage requirements — satisfied

Current storage use is approximately **600 GB**. Foreseeable active-storage demand is not expected to exceed 2 TB soon.

Selected primary SSD: **Crucial T710 2 TB `CT2000T710SSD8`**.

- install in CPU-direct `M.2_1` at PCIe 5.0 x4;
- use the bare/non-heatsink variant under the ASUS motherboard M.2 heatsink;
- hold Windows, applications, repositories, build caches, WSL2, containers, Android emulator data, active VMs/databases, games and other active data on this drive;
- no second NVMe initially;
- no SSD cache, Storage Spaces-style tiering or RAID.

Existing healthy SATA SSD/HDD devices may be reused for archives/cold data after SMART/health validation. Important data must not exist only on an old SATA drive.

## GPU / expansion

Reuse the RTX 3060 until failure or a concrete upgrade need appears. A future replacement retires it rather than creating a dual-GPU design.

Do not pre-size today's motherboard/PSU/case for an unknown flagship GPU.

## Networking

- 1 GbE is sufficient;
- the board's 2.5 GbE is more than adequate;
- 5/10 GbE carries no purchase premium value.

## PSU requirements — satisfied

Selected: **be quiet! Pure Power 13 M 850W `BP027EU`**.

Requirements:

- ATX 3.1;
- 850 W;
- native current-generation GPU-power cabling;
- fully modular;
- strong protection/transient/ripple behavior;
- quiet fan implementation;
- long manufacturer warranty;
- normal Romanian/EU warranty path.

Fallback: **Corsair RM850x 2024 `CP-9020270-EU`** only if checkout price/warranty is materially better.

Never reuse modular cables from another PSU.

## UPS / mains protection — satisfied

No UPS and no dedicated surge protector initially. Use a properly earthed wall outlet; if multiple outlets are needed, use a reputable ordinary 16 A Schuko strip.

Revisit external mains protection only if actual evidence of poor power quality appears.

## Procurement constraints

- maximum three providers overall;
- target at most two hardware providers;
- exact SKU/revision, warranty clarity and product condition outrank small nominal savings;
- current RAM target may come from a different hardware retailer if materially cheaper than the main basket;
- refresh all live prices/stock immediately before payment.

## Decision philosophy

For every premium ask:

1. Does the real workload need it?
2. Does it materially improve stability, serviceability, endurance or performance?
3. Is the benefit durable over ownership?
4. Can it be added/replaced later more cheaply if necessary?
5. Are we paying for a concrete requirement or a hypothetical scenario?

When performance and stability conflict, prefer stability unless the performance loss materially affects the workstation's core purpose.
