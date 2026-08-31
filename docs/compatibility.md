# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. The existing RTX 3060 12 GB is reused initially; the CPU, motherboard, chassis, cooling architecture, exact CPU cooler, storage architecture and exact initial system SSD are now selected.

## CPU/platform ↔ motherboard

Selected:

- **AMD Ryzen 9 9950X3D**
- **ASUS ProArt X870E-Creator WiFi**

Key operating policy:

- use current stable BIOS before serious validation;
- keep CPU at stock/conservative power settings;
- preserve the board's validated 256 GB memory path;
- use USB BIOS FlashBack if the shipping BIOS is not suitable for the CPU.

## Motherboard ↔ memory

Selected architectural target:

- credible path to **256 GB**, expected 4×64 GB;
- exact long-term DIMMs remain deferred;
- ECC UDIMM preferred only if exact modules and OS-visible ECC behavior are credible and stable.

Current Phase-1 purchase target:

- Kingston FURY Beast Black EXPO 32 GB (2×16 GB) DDR5-6000 CL30
- exact SKU: **`KF560C30BBEK2-32`**
- Kingston lists the exact kit for the ProArt X870E-Creator WiFi.

Bring-up policy:

- use motherboard-recommended two-DIMM slots;
- boot at Auto/JEDEC first;
- treat EXPO as optional;
- replace rather than expand the temporary kit when moving to the validated 256 GB endpoint.

## CPU ↔ cooling

Selected:

- **Noctua NH-D15 G2, standard base**
- install using the included **7 mm AM5 offset mount**
- CPU remains at stock/conservative power settings.

Why standard rather than LBC:

- Noctua explicitly recommends the standard G2 as the best all-rounder;
- on AM5 with the included offset mount, Noctua rates the standard version as excellent and reports its best absolute AM5 result with this configuration;
- LBC's material advantage is mainly AM5 without offset mounting or specialized flat/direct-die applications;
- standard preserves broader future-socket versatility.

The **ASUS ProArt X870E-Creator WiFi is explicitly listed as compatible by Noctua**.

## Cooling ↔ memory ↔ case

Relevant dimensions:

- NH-D15 G2 stock height: **168 mm**;
- normal dual-fan RAM clearance: approximately **32 mm**;
- Kingston `KF560C30BBEK2-32` module height: **34.9 mm**;
- required front-fan lift: approximately **3 mm**;
- resulting practical cooler height: approximately **171 mm**;
- Fractal North XL Mesh CPU-cooler limit: **185 mm**.

Result:

- approximately **14 mm remaining height margin**;
- no case-side-panel clearance concern with the selected Phase-1 RAM;
- front fan should be raised only as much as required.

The eventual 256 GB memory purchase should still prefer reasonably low-profile modules when technically equivalent, because future 64 GB DIMM height is not yet fixed.

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

This preserves the CPU-connected Gen5 slot for the future work drive while avoiding unnecessary impact on the primary GPU path.

## Storage ↔ workload

Selected architecture:

- permanent 2 TB system/tools SSD now;
- add a physically separate 4 TB-or-larger work drive later.

The second drive is justified by operational separation rather than benchmark aggregation:

- isolate VM/container/database/build-cache writes from the OS/tools drive;
- separate replacement/recovery domains;
- distribute sustained I/O and controller thermals;
- allow future capacity and Gen5 choice without replacing the system SSD.

This is not a backup strategy.

## Motherboard ↔ GPU / expansion

- Existing RTX 3060 12 GB will be used initially.
- The selected North XL Mesh, 1200 W PSU architecture and air-cooling layout preserve a path to a substantially larger future high-VRAM GPU.
- The selected storage topology avoids `M.2_2` so the primary GPU does not lose lanes merely to host the planned two-drive storage layout.
- CPU-connected x8/x8 remains useful future expansion headroom but is not a current requirement.

## Case ↔ cooling / GPU / motherboard

Selected chassis:

- **Fractal Design North XL Mesh**

Validated against selected cooler:

- 185 mm CPU-cooler envelope;
- ~171 mm practical NH-D15 G2 height with current Kingston RAM;
- ample margin remains.

Selected airflow:

- 3×140 mm included front intake;
- 1×140 mm rear exhaust;
- no top/side fans initially.

The front remains unobstructed by a radiator, which is desirable for a future high-power GPU.

## PSU ↔ CPU / GPU / expansion

Selected architecture:

- **1200 W ATX 3.1 / PCIe 5.1**
- native **12V-2x6**
- current provisional target: Seasonic VERTEX GX-1200 ATX 3.1.

The PSU is intentionally sized around a plausible future very-high-power single GPU, not merely the current RTX 3060.

## UPS ↔ PSU / full system

Selected Phase-1 architecture:

- line-interactive;
- pure sine-wave output;
- around 1600 VA / 1000 W;
- AVR;
- USB monitoring/graceful shutdown;
- user-replaceable battery.

Current provisional target: CyberPower CP1600EPFCLCD.

The UPS is sized for the current RTX 3060 system and must be reassessed when a materially higher-power GPU is installed.

## Procurement dependencies

For currently selected purchase-ready parts:

- prefer **PC Garage first**;
- use **eMAG second**;
- when the price difference is small, prefer PC Garage rather than optimizing for the last few lei.

This applies to the selected Samsung 990 PRO 2 TB and standard NH-D15 G2. Purchase-time verification must still confirm exact SKU, normal Romanian/EU warranty and no new firmware/compatibility issue.
