# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. The existing RTX 3060 12 GB is reused initially; the CPU, motherboard, Phase-1 memory, chassis, cooling architecture, exact CPU cooler, storage architecture, exact initial system SSD, rear exhaust fan and Phase-1 UPS are now selected.

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

Selected Phase-1 memory:

- **GOODRAM 32 GB DDR5-5600 CL46**
- exact SKU: **`GR5600D564L46/32G`**
- topology: **1×32 GB**
- standard 1.1 V desktop DDR5 UDIMM
- approximately 31.25 mm tall.

The one-DIMM topology deliberately gives up dual-channel bandwidth in exchange for roughly 800 lei lower sunk cost versus the prior Kingston 2×16 target and the simplest possible commissioning load on the memory controller.

Bring-up policy:

- use the motherboard-recommended one-DIMM slot, expected to be A2; confirm against the current manual;
- boot at Auto/JEDEC only;
- do not manually overclock the temporary DIMM;
- accept a lower trained data rate if firmware chooses one for stability;
- replace rather than expand the Phase-1 DIMM when moving to the validated 256 GB endpoint.

The exact GOODRAM SKU was not found in the current ProArt QVL during the purchase pass. That is accepted for Phase 1 because it is a standard JEDEC-class single UDIMM rather than a tuned EXPO/XMP configuration; QVLs are not exhaustive. Unexpected training problems would reopen the exact temporary SKU, not the platform architecture.

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
- GOODRAM `GR5600D564L46/32G` module height: approximately **31.25 mm**;
- required front-fan lift: **none**;
- Fractal North XL Mesh CPU-cooler limit: **185 mm**.

Result:

- cooler stays at its stock **168 mm** height;
- approximately **17 mm remaining height margin**;
- no case-side-panel clearance concern with the selected Phase-1 RAM;
- no front-fan relocation is required.

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
- 168 mm practical NH-D15 G2 height with the selected low-profile Phase-1 GOODRAM;
- approximately 17 mm height margin remains.

Selected airflow:

- 3×140 mm included front intake;
- 1× Noctua NF-A14x25 G2 PWM 140 mm rear exhaust;
- no top/side fans initially.

The front remains unobstructed by a radiator, which is desirable for a future high-power GPU.

## PSU ↔ CPU / GPU / expansion

Selected architecture:

- **1200 W ATX 3.1 / PCIe 5.1**
- native **12V-2x6**
- current provisional target: Seasonic VERTEX GX-1200 ATX 3.1.

The PSU is intentionally sized around a plausible future very-high-power single GPU, not merely the current RTX 3060.

The exact PSU remains open because Romanian listings still mix old VERTEX ATX 3.0/12VHPWR stock with the required current ATX 3.1/12V-2x6 revision.

## UPS ↔ PSU / full system

Selected Phase-1 UPS:

- **CyberPower CP1600EPFCLCD**
- 1600 VA / 1000 W;
- line-interactive;
- pure sine-wave output;
- Active-PFC compatible;
- AVR;
- USB HID / PowerPanel monitoring and graceful shutdown;
- user-replaceable `RBP0142` battery.

The UPS is sized for the current RTX 3060 system and must be reassessed when a materially higher-power GPU is installed or measured wall load approaches roughly 700–800 W.

## Procurement dependencies

For selected purchase-ready parts:

- prefer **PC Garage first**;
- use **eMAG second**;
- when the price difference is small, prefer PC Garage rather than optimizing for the last few lei;
- for explicitly temporary Phase-1 RAM, a **material** price saving can override brand/performance preference because sunk cost is intentionally minimized.

Current examples:

- GOODRAM `GR5600D564L46/32G`: PC Garage around 2,199.99 lei and selected over the ~2,998.99 lei Kingston temporary kit;
- Samsung 990 PRO 2 TB: PC Garage preferred over eMAG when price difference is small;
- NH-D15 G2 standard: PC Garage first, eMAG second, but confirm standard rather than LBC/HBC;
- CyberPower CP1600EPFCLCD: current PC Garage premium is small enough to prefer PC Garage.
