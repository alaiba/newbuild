# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. The existing RTX 3060 12 GB is reused initially; the CPU, motherboard, **64 GB Phase-1 memory capacity**, chassis, cooling architecture, exact CPU cooler, storage architecture, exact initial system SSD, exact PSU, rear exhaust fan and Phase-1 UPS are selected.

## CPU/platform ↔ motherboard

Selected:

- **AMD Ryzen 9 9950X3D**
- **ASUS ProArt X870E-Creator WiFi**

Operating policy:

- use current stable BIOS before serious validation;
- keep CPU at stock/conservative power settings;
- preserve the board's validated 256 GB memory path;
- use USB BIOS FlashBack if the shipping BIOS is unsuitable for the CPU.

## Motherboard ↔ memory

Long-term architectural target:

- credible path to **256 GB**, expected 4×64 GB;
- exact long-term DIMMs deferred;
- ECC UDIMM preferred only if exact modules, four-DIMM stability and OS-visible ECC behavior are credible.

Selected Phase-1 capacity:

- **64 GB (2×32 GB)**.

Preferred exact target:

- **Crucial `CT2K32G56C46U5`**;
- DDR5-5600 CL46;
- 1.1 V;
- ordinary unbuffered desktop UDIMMs;
- low-profile bare modules.

Why this topology is appropriate:

- 2×32 GB restores dual-channel bandwidth;
- two DIMMs remain a straightforward AM5 topology;
- 5600 MT/s and 1.1 V are conservative compared with aggressive high-voltage EXPO tuning;
- the final BOM remains far below the planning level, so the capacity upgrade does not displace permanent hardware.

Compatibility fallback:

- **Kingston `KF556C36BBEK2-64`**, explicitly listed by Kingston for the ProArt X870E-Creator WiFi.

Bring-up policy:

- install in motherboard-recommended A2/B2 slots;
- boot at Auto/JEDEC first;
- do not enable EXPO/XMP during baseline validation;
- prioritize stability over headline timings;
- run extended memory testing.

## CPU ↔ cooling

Selected:

- **Noctua NH-D15 G2 standard base**
- included **7 mm AM5 offset mount**
- CPU at stock/conservative settings.

The **ASUS ProArt X870E-Creator WiFi is explicitly listed as compatible by Noctua**.

## Cooling ↔ memory ↔ case

Relevant envelope:

- NH-D15 G2 stock height: **168 mm**;
- normal dual-fan RAM clearance: approximately **32 mm**;
- North XL CPU-cooler limit: **185 mm**.

Selected Crucial 64 GB kit:

- low-profile bare modules around the low-30-mm height class;
- expect **zero or only minimal front-fan lift**;
- even a ~2 mm lift would put practical cooler height around 170 mm;
- at least ~15 mm case-side margin would remain.

Kingston fallback:

- ~34.9 mm module height;
- ~3 mm front-fan lift;
- ~171 mm practical cooler height;
- ~14 mm case margin.

Therefore both selected/preferred 64 GB paths fit comfortably.

## Motherboard ↔ storage

Selected initial SSD:

- **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`**
- permanent system/tools role
- PCIe 4.0 x4, bare M.2 2280 drive under the motherboard heatsink.

Preferred ProArt topology:

- **`M.2_3`**: Samsung 990 PRO 2 TB system/tools SSD
- **`M.2_1`**: future 4 TB-or-larger work/VM/container/data SSD
- keep **`M.2_2`** unused unless its graphics-lane trade-off is intentionally accepted
- **`M.2_4`** remains available for later lower-priority storage.

## Storage ↔ workload

Selected architecture:

- permanent 2 TB system/tools SSD now;
- add a separate 4 TB-or-larger work drive later.

The second drive is for workload/recovery/thermal separation rather than benchmark aggregation. This is not a backup strategy.

## Motherboard ↔ GPU / expansion

- Existing RTX 3060 12 GB is reused initially.
- North XL Mesh, the selected 1200 W PSU and air cooling preserve a path to a substantially larger future high-VRAM GPU.
- The storage topology avoids `M.2_2`, preserving the primary GPU path.
- CPU-connected x8/x8 remains useful future headroom but is not a current requirement.

## Case ↔ cooling / GPU / motherboard

Selected chassis:

- **Fractal Design North XL Mesh**

Selected airflow:

- 3×140 mm included front intake;
- 1× Noctua NF-A14x25 G2 PWM rear exhaust;
- no top/side fans initially.

The front remains unobstructed by a radiator, preserving clean future-GPU intake.

## PSU ↔ CPU / GPU / case

Selected exact PSU:

- **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision**.

Compatibility points:

- 1200 W provides the selected margin for a future ~600 W single GPU plus the 9950X3D platform;
- the ProArt's motherboard and dual CPU EPS requirements are covered without adapters;
- the PSU is about **160 mm** deep versus roughly **290 mm** available PSU clearance in North XL;
- the future high-power GPU should use the Seasonic-supplied 12V-2x6 cable;
- future GPU width and connector bend radius must be revalidated when that GPU is selected.

Purchase/receipt acceptance:

- box/listing must say **ATX 3.1**;
- GPU cable must be **12V-2x6**;
- reject old ATX 3.0 / 12VHPWR VERTEX inventory;
- retain exact serial/model/warranty evidence;
- use only Seasonic-approved modular cables.

## UPS ↔ PSU / full system

Selected Phase-1 UPS:

- **CyberPower CP1600EPFCLCD**
- 1600 VA / 1000 W
- line-interactive pure sine wave
- Active-PFC compatible
- AVR
- USB HID / PowerPanel
- user-replaceable `RBP0142` battery.

The UPS is intentionally sized for the current RTX 3060 system, not the PSU's 1200 W nameplate. Reassess when a materially higher-power GPU is installed or measured wall load approaches roughly 700–800 W.

## Procurement dependencies

For purchase-ready parts:

- **PC Garage and Altex are co-preferred Romanian retailers**;
- **eMAG is also acceptable**;
- exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order;
- small price differences do not matter;
- material price differences may justify another reputable seller, especially for temporary memory.

For Phase-1 memory:

- target Crucial `CT2K32G56C46U5` around the current ~4.7–4.8k lei market class;
- compare Kingston `KF556C36BBEK2-64` if Crucial availability/warranty/pricing degrades materially;
- do not pay extra for 6000 MT/s merely for the headline frequency.
