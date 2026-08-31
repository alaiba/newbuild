# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. The existing RTX 3060 12 GB is reused initially; the CPU, motherboard, chassis, cooling architecture, exact CPU cooler, storage architecture, exact initial system SSD, rear exhaust fan and Phase-1 UPS are selected. The **final Phase-1 memory capacity remains open between a 32 GB baseline and optional 64 GB 2×32 configuration**.

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

Architectural target:

- credible path to **256 GB**, expected 4×64 GB;
- exact long-term DIMMs deferred;
- ECC UDIMM preferred only if exact modules, four-DIMM stability and OS-visible ECC behavior are credible.

### Phase-1 baseline — 32 GB

- GOODRAM `GR5600D564L46/32G`
- 1×32 GB
- DDR5-5600 CL46, 1.1 V
- approximately 31.25 mm tall
- current PC Garage reference: ~2,199.99 lei.

This is the minimum-sunk-cost commissioning baseline. It is not an instruction to buy 32 GB before the final BOM review.

### Optional Phase-1 tier — 64 GB

Preferred topology: **2×32 GB**.

Current serious candidates:

- **Crucial `CT2K32G56C46U5`** — 64 GB (2×32), DDR5-5600 CL46, 1.1 V; current value control around 4.7–4.8k lei in the broader Romanian market.
- **Kingston `KF556C36BBEK2-64`** — 64 GB (2×32), DDR5-5600 CL36 EXPO; explicitly listed by Kingston for the ProArt X870E-Creator WiFi.
- **Kingston `KF560C36BBEK2-64`** — 64 GB (2×32), DDR5-6000 CL36 EXPO; explicitly listed by Kingston for the ProArt and sometimes price-promoted close to 5.0k lei.

A single 64 GB `KVR56U46BD8-64` is also explicitly listed by Kingston for the ProArt and is electrically conservative at 5600 CL46 / 1.1 V, but current pricing around 5.1k lei+ makes it poor value versus 2×32 because it remains single-channel.

### Final Phase-1 memory decision

Defer the 32-vs-64 choice until the complete initial BOM total is known.

Working price guide:

- ≤ ~4.5k lei for a credible 2×32 kit: 64 GB strongly attractive;
- ~4.5–4.8k: serious consideration;
- materially above ~5.0k: 32 GB baseline normally preferred unless remaining budget is abundant.

Regardless of capacity:

- boot at Auto/JEDEC first;
- treat EXPO/XMP as optional;
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

32 GB baseline:

- GOODRAM height ~31.25 mm;
- no fan lift;
- cooler remains 168 mm;
- ~17 mm case margin.

64 GB Kingston FURY candidates:

- module height ~34.9 mm;
- front fan needs only ~3 mm lift;
- practical cooler height ~171 mm;
- ~14 mm case margin.

Therefore **both the 32 GB baseline and the serious 64 GB alternatives fit comfortably**. The final 256 GB purchase should still prefer reasonably low-profile modules when technically equivalent.

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
- North XL Mesh, the 1200 W PSU architecture and air cooling preserve a path to a substantially larger future high-VRAM GPU.
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

## PSU ↔ CPU / GPU / expansion

Selected architecture:

- **1200 W ATX 3.1 / PCIe 5.1**
- native **12V-2x6**
- current provisional target: current-revision Seasonic VERTEX GX-1200.

The exact PSU remains open because Romanian listings still mix old ATX 3.0/12VHPWR stock with the required current ATX 3.1/12V-2x6 revision.

## UPS ↔ PSU / full system

Selected Phase-1 UPS:

- **CyberPower CP1600EPFCLCD**
- 1600 VA / 1000 W
- line-interactive pure sine wave
- Active-PFC compatible
- AVR
- USB HID / PowerPanel
- user-replaceable `RBP0142` battery.

Reassess when a materially higher-power GPU is installed or measured wall load approaches roughly 700–800 W.

## Procurement dependencies

For purchase-ready parts:

- prefer **PC Garage first**;
- use **eMAG second**;
- prefer PC Garage when the difference is small;
- for temporary Phase-1 RAM, a material saving can override retailer/brand preference because sunk cost is intentionally minimized.

For memory specifically, **do not order until the final BOM review chooses between 32 GB and 64 GB**.
