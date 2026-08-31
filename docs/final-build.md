# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, motherboard, exact Phase-1 memory, 256 GB architectural memory target, high-end air-cooling architecture, exact CPU cooler, staged storage architecture, exact initial system SSD, 1200 W ATX 3.1 PSU architecture, Fractal Design North XL Mesh chassis, exact rear exhaust fan, exact Phase-1 UPS and existing GPU are selected**. Several long-term/purchase-time items remain deferred or provisional.

## Status vocabulary for this document

- **Selected** — closed decision; use as a fixed input to subsequent component selection unless explicitly reopened.
- **Target selected** — design target is fixed, but implementation details remain open.
- **Provisional target** — preferred current candidate, intentionally not final; may change if dependent validation fails or purchase-time pricing changes materially.
- **Open** — no preferred model/configuration has been nominated yet.

## Selected components

| Component | Selected model | Status | Notes |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | AM5 platform; fixed input |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | Chosen for the strongest explicit 4×64 GB / 256 GB firmware evidence and ECC-specific firmware trail. |
| Phase-1 memory | **GOODRAM 32 GB DDR5-5600 CL46 `GR5600D564L46/32G`, 1×32 GB** | **Selected** | Deliberately temporary commissioning DIMM. Standard 1.1 V JEDEC-class operation, low controller complexity and ~800 lei less than the prior Kingston 2×16 target at PC Garage. Single-channel bandwidth is an accepted Phase-1 trade-off. Replace rather than expand at the 256 GB upgrade. |
| Long-term memory | **256 GB architectural target, expected 4×64 GB** | **Target selected / purchase deferred** | Prefer ECC UDIMM only if exact 64 GB modules, four-DIMM support, stability and OS-visible ECC reporting are credible at upgrade time; otherwise use validated non-ECC. |
| CPU cooler | **Noctua NH-D15 G2 — standard base, 7 mm AM5 offset mount** | **Selected** | Noctua's default recommendation and its best AM5 result with offset mounting. Explicitly compatible with ProArt X870E-Creator WiFi. The selected 31.25 mm GOODRAM DIMM fits under normal ~32 mm RAM clearance, so no front-fan lift is needed; cooler remains 168 mm tall versus North XL's 185 mm limit. |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | Permanent Gen4 TLC + DRAM system/tools drive. Install bare drive under the ProArt `M.2_3` heatsink. PC Garage preferred over eMAG when price difference is small. |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / purchase deferred** | Dedicated source/VM/container/database/work drive. Reserve CPU-connected `M.2_1`; reassess Gen4 vs Gen5 and 4 TB vs 8 TB when capacity is actually needed. |
| PSU | **Seasonic VERTEX GX-1200 ATX 3.1** | **Provisional target** | 1200 W ATX 3.1 / PCIe 5.1 architecture selected. Require native 12V-2x6 and verify exact current revision at purchase. |
| Case | **Fractal Design North XL Mesh** | **Selected** | 413 mm GPU clearance, 185 mm CPU-cooler clearance, front + PSU filtration, 3×140 mm PWM front fans included, 290 mm PSU clearance, top 360 mm AIO fallback support. |
| Rear case fan | **Noctua NF-A14x25 G2 PWM, square-frame 140 mm** | **Selected** | Permanent rear exhaust. 0–1500 RPM PWM, SSO2 bearing, >150,000 h MTTF and six-year warranty. Standard brown/beige is baseline; chromax.black is technically equivalent if similarly priced. |
| Case-fan layout | **3× included 140 mm front intake + 1× Noctua 140 mm rear exhaust** | **Selected** | No top/side fans initially. Add only if measured thermals justify them. |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially; preserve future path to one very high-end/high-VRAM GPU |
| UPS | **CyberPower CP1600EPFCLCD** | **Selected** | 1600 VA / 1000 W, pure-sine line-interactive, Active-PFC compatible, AVR, USB HID/PowerPanel, user-replaceable `RBP0142` battery. Selected for the current RTX 3060 system; reassess at future high-power GPU upgrade. |
| OS | — | Open | |

## Motherboard selection rationale

The ProArt is closed because its firmware history explicitly addresses four-64-GB / 256 GB operation, four-DIMM stability and ECC UDIMM behavior. The ASRock X870 Taichi Creator remains attractive on price/topology but did not match ASUS's exact validation evidence.

Detailed evidence: `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.

## Memory implementation strategy

### Phase 1 — selected

Exact selected memory:

- **GOODRAM 32 GB DDR5-5600 CL46 — `GR5600D564L46/32G`**;
- topology: **1×32 GB**;
- desktop DDR5 UDIMM, 288-pin;
- 5600 MT/s, CL46, 1.1 V;
- no EXPO/XMP dependency;
- approximately 31.25 mm high;
- lifetime manufacturer warranty.

Current purchase position on 2026-08-31:

- PC Garage: approximately **2,199.99 lei**, in stock;
- prior Kingston `KF560C30BBEK2-32` 2×16 target at PC Garage: approximately **2,998.99 lei**.

The ~800 lei saving is intentionally taken because this memory is temporary. The 1×32 configuration gives up dual-channel bandwidth but reduces sunk cost and keeps the commissioning setup electrically simple.

Bring-up:

1. install the module in the motherboard-recommended one-DIMM slot, expected to be **A2**; verify against the current ProArt manual;
2. update BIOS;
3. boot at Auto/JEDEC;
4. do not overclock or tune the temporary module;
5. accept a lower automatically trained data rate if firmware chooses one for stability;
6. run extended memory testing before commissioning.

Do not buy a second unmatched 32 GB module merely to recover dual-channel bandwidth. If Phase 1 lasts long enough for bandwidth to become a productivity problem, reassess whether to accelerate the final 256 GB purchase instead.

Procurement preference remains **PC Garage first, eMAG second** when the price difference is small.

### Eventual 256 GB

The endpoint remains **4×64 GB or equivalent**, but the exact purchase is deferred.

At upgrade time:

1. install the then-current stable ProArt BIOS;
2. re-check ASUS QVL for exact 64 GB modules and four-DIMM support;
3. prefer **4×64 GB ECC UDIMM** only if exact parts are available, credible and stable;
4. otherwise select a strongly validated **4×64 GB non-ECC UDIMM** configuration;
5. start at JEDEC/Auto and accept 5200 MT/s or lower if required for stability;
6. avoid EXPO/XMP merely to preserve headline frequency at 256 GB;
7. perform extended memory stability testing;
8. if ECC is used, verify Windows WHEA and/or Linux EDAC/RAS reporting.

**RDIMM is incompatible with this AM5 platform.**

## Cooling strategy

Selected configuration:

- **Noctua NH-D15 G2, standard medium-convexity base**;
- use the included **7 mm AM5 offset mounting position**;
- Ryzen 9 9950X3D remains at stock/conservative power settings;
- no PBO/uncapped power merely to exploit thermal headroom.

Why standard G2 rather than G2 LBC:

- Noctua explicitly describes the standard G2 as its default/best-all-rounder recommendation;
- on AM5 with the included offset mount, Noctua reports the standard version as performing on par with or slightly better than LBC;
- LBC is mainly advantageous on AM5 **without** offset mounting or for specialized flat-IHS/direct-die cases;
- the standard base preserves broader future-socket versatility, which fits the approximately 10-year ownership/serviceability goal.

Clearance with the selected Phase-1 memory:

- cooler stock height: **168 mm**;
- GOODRAM module height: **31.25 mm**;
- normal dual-fan RAM clearance: approximately **32 mm**;
- required front-fan lift: **none**;
- Fractal North XL Mesh CPU-cooler limit: **185 mm**;
- remaining height margin: approximately **17 mm**.

The ProArt X870E-Creator WiFi is explicitly listed as compatible by Noctua.

A top-mounted 360 mm AIO remains an emergency fallback only if real sustained workloads demonstrate an unacceptable thermal/acoustic result after fan-curve tuning; it is not part of the selected build.

## Storage strategy

Selected initial SSD:

- **Samsung 990 PRO 2 TB — `MZ-V9P2T0BW`**;
- permanent system/tools role;
- PCIe 4.0 x4, TLC + DRAM;
- bare drive under the motherboard heatsink;
- preferred ProArt slot: **`M.2_3`**.

Long-term storage remains staged:

- later add a **4 TB-or-larger** work/VM/container/data SSD;
- reserve CPU-connected **`M.2_1`** for that future drive;
- avoid `M.2_2` unless its graphics-lane trade-off is intentionally accepted;
- reassess 4 TB vs 8 TB and Gen4 vs Gen5 only when the second drive is actually needed;
- no RAID; external/network backup remains required.

Retailer preference for the selected 990 PRO is **PC Garage first, eMAG second when the price difference is small**.

## PSU strategy

- permanent architecture: **1200 W ATX 3.1 / PCIe 5.1**, native **12V-2x6**;
- provisional target: **Seasonic VERTEX GX-1200 ATX 3.1**;
- verify current ATX 3.1 revision and native cable at purchase.

## Chassis and airflow

Selected chassis: **Fractal Design North XL Mesh**.

Initial fan layout:

- front: **3× included Fractal Aspect 14 PWM intake**;
- rear: **1× Noctua NF-A14x25 G2 PWM exhaust**;
- top: empty;
- side: empty.

Rear-fan procurement:

- exact baseline: square-frame **NF-A14x25 G2 PWM**, standard 1500-RPM version, EAN `9010018100617` for brown/beige;
- current Romanian single-fan market is roughly **180–210 lei**;
- chromax.black is an equivalent substitute if the price difference is small;
- PC Garage first, eMAG second when they stock the single fan at a sensible price;
- do **not** buy an unnecessary two-pack merely because that is the only preferred-retailer listing indexed at the moment.

Add top/side fans only if measured CPU/GPU/SSD/VRM thermals justify them.

## UPS

Selected Phase-1 UPS: **CyberPower CP1600EPFCLCD**.

Key characteristics:

- line-interactive;
- pure sine-wave output on battery;
- Active-PFC compatible;
- **1600 VA / 1000 W**;
- AVR;
- six Schuko battery-backed/surge-protected outlets per the current official EU/Romanian specification;
- USB HID monitoring plus PowerPanel Business support;
- included USB cable;
- user-replaceable **RBP0142** battery pack, 24 V / 2×12 V 9 Ah;
- manufacturer runtime approximately 9.7 minutes at 500 W and 2.6 minutes at 1000 W;
- official Romanian warranty: 2 years UPS / 2 years battery.

Current purchase position on 2026-08-31:

- PC Garage: approximately **1,589.80 lei, in stock**;
- cheapest broader Romanian offers: roughly **1.47–1.55k lei**.

The PC Garage premium is small enough to follow the retailer preference and buy there.

The UPS is deliberately sized for the current RTX 3060 workstation rather than the hypothetical future 600 W GPU. Reassess the UPS at the GPU upgrade or if measured system load approaches roughly 700–800 W.

## Remaining promotion / purchase-time gates

### Phase-1 memory

The exact module is selected. Before/at installation:

- confirm exact `GR5600D564L46/32G` desktop UDIMM;
- prefer PC Garage while its price remains close to the market;
- use the recommended one-DIMM motherboard slot;
- boot only at Auto/JEDEC and run extended stability testing.

### CPU cooler

The exact model is selected. Purchase-time work is limited to procurement sanity checks:

- prefer PC Garage first, eMAG second;
- confirm the listing is **standard NH-D15 G2**, not LBC or HBC;
- do not pay a material premium for LBC;
- install using the **-7 mm AM5 offset** position;
- keep the front fan at its normal position with the selected 31.25 mm Phase-1 DIMM.

### Rear case fan

The exact model is selected:

- buy one **Noctua NF-A14x25 G2 PWM** square-frame fan;
- prefer a single unit around the normal market price rather than an unnecessary two-pack;
- chromax.black is acceptable if similarly priced;
- control by motherboard PWM and tune for low steady RPM under normal development loads.

### PSU

- verify current ATX 3.1 / 12V-2x6 revision;
- verify warranty and case/cable routing.

### UPS

The exact hardware is selected. Bring-up/acceptance work remains:

- prefer PC Garage while its premium remains small;
- confirm exact `CP1600EPFCLCD` EU/Schuko unit and expected six outlets on receipt;
- connect USB and configure automatic graceful shutdown;
- measure actual load and runtime;
- perform a controlled mains-loss shutdown test.

### SSD

The exact system SSD is selected. Immediately before purchase/install:

- confirm no new unresolved 990 PRO firmware/health issue;
- prefer PC Garage over eMAG when the price difference is small;
- confirm normal warranty and bare `MZ-V9P2T0BW` SKU;
- update/record firmware at bring-up.

## Final compatibility checks

Before purchase/assembly, verify:

- 9950X3D support on shipping ProArt BIOS or have USB BIOS FlashBack ready;
- selected GOODRAM Phase-1 DIMM trains stably at Auto/JEDEC;
- standard NH-D15 G2 installed with 7 mm AM5 offset and stock front-fan position;
- selected 990 PRO firmware/warranty and `M.2_3` placement;
- Seasonic exact ATX 3.1 revision and native 12V-2x6 cable;
- RTX 3060 fit and future-GPU physical/cable clearance;
- North XL front-I/O headers against ProArt;
- rear NF-A14x25 G2 PWM on a controllable 4-pin fan header;
- UPS output wattage/waveform versus measured system load.

## Bring-up and validation

- update BIOS before serious memory testing;
- baseline boot at Auto/JEDEC with the single 32 GB GOODRAM DIMM;
- extended memory stability testing;
- record negotiated memory rate/timings;
- if ECC memory is ever installed later, validate actual ECC event reporting;
- update Samsung 990 PRO firmware, record SMART baseline and perform sustained-I/O temperature testing;
- sustained CPU thermal/load testing with NH-D15 G2;
- combined CPU/GPU thermal validation with the selected four-fan case layout;
- tune front/rear fan curves for sustained workloads rather than transient Ryzen spikes;
- inspect PSU/GPU power connectors for full insertion and strain-free routing;
- sleep/resume, WSL2 and virtualization validation;
- 10 GbE driver/firmware and sleep/resume validation;
- connect the CP1600EPFCLCD by USB, configure graceful shutdown, measure load/runtime and perform a controlled power-loss test.
