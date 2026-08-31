# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, motherboard, 256 GB architectural memory target, 32 GB Phase-1 memory floor, high-end air-cooling architecture, exact CPU cooler, staged storage architecture, exact initial system SSD, 1200 W ATX 3.1 PSU architecture, Fractal Design North XL Mesh chassis, exact rear exhaust fan, Phase-1 UPS architecture and existing GPU are selected**. Several purchase-time SKUs remain provisional.

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
| Memory | **Kingston FURY Beast Black EXPO 32 GB (2×16) DDR5-6000 CL30 `KF560C30BBEK2-32`** | **Provisional Phase-1 purchase target** | PC Garage-first target. Kingston explicitly lists this exact kit for the ProArt X870E-Creator WiFi. Boot at Auto/JEDEC first; EXPO is optional. Replace rather than expand when moving to the 256 GB endpoint. |
| Long-term memory | **256 GB architectural target, expected 4×64 GB** | **Target selected / purchase deferred** | Prefer ECC UDIMM only if exact 64 GB modules, four-DIMM support, stability and OS-visible ECC reporting are credible at upgrade time; otherwise use validated non-ECC. |
| CPU cooler | **Noctua NH-D15 G2 — standard base, 7 mm AM5 offset mount** | **Selected** | Noctua's default recommendation and its best AM5 result with offset mounting. Explicitly compatible with ProArt X870E-Creator WiFi. Kingston RAM requires only ~3 mm front-fan lift, yielding ~171 mm total height versus North XL's 185 mm clearance. Prefer PC Garage first, eMAG second. |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | Permanent Gen4 TLC + DRAM system/tools drive. Install bare drive under the ProArt `M.2_3` heatsink. PC Garage preferred over eMAG when price difference is small. |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / purchase deferred** | Dedicated source/VM/container/database/work drive. Reserve CPU-connected `M.2_1`; reassess Gen4 vs Gen5 and 4 TB vs 8 TB when capacity is actually needed. |
| PSU | **Seasonic VERTEX GX-1200 ATX 3.1** | **Provisional target** | 1200 W ATX 3.1 / PCIe 5.1 architecture selected. Require native 12V-2x6 and verify exact revision at purchase. |
| Case | **Fractal Design North XL Mesh** | **Selected** | 413 mm GPU clearance, 185 mm CPU-cooler clearance, front + PSU filtration, 3×140 mm PWM front fans included, 290 mm PSU clearance, top 360 mm AIO fallback support. |
| Rear case fan | **Noctua NF-A14x25 G2 PWM, square-frame 140 mm** | **Selected** | Permanent rear exhaust. 0–1500 RPM PWM, SSO2 bearing, >150,000 h MTTF and six-year warranty. Standard brown/beige is baseline; chromax.black is technically equivalent if similarly priced. |
| Case-fan layout | **3× included 140 mm front intake + 1× Noctua 140 mm rear exhaust** | **Selected** | No top/side fans initially. Add only if measured thermals justify them. |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially; preserve future path to one very high-end/high-VRAM GPU |
| UPS | **CyberPower CP1600EPFCLCD** | **Provisional target** | Phase-1 architecture selected: line-interactive, pure sine, ~1600 VA / 1000 W. Reassess UPS capacity when a materially higher-power GPU is installed. |
| OS | — | Open | |

## Motherboard selection rationale

The ProArt is closed because its firmware history explicitly addresses four-64-GB / 256 GB operation, four-DIMM stability and ECC UDIMM behavior. The ASRock X870 Taichi Creator remains attractive on price/topology but did not match ASUS's exact validation evidence.

Detailed evidence: `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.

## Memory implementation strategy

### Phase 1

Current purchase target:

- **Kingston FURY Beast Black EXPO 32 GB (2×16 GB) DDR5-6000 CL30 — `KF560C30BBEK2-32`**;
- Kingston explicitly lists this exact kit as compatible with the **ASUS ProArt X870E-Creator WiFi**;
- use the motherboard-recommended two-DIMM slots;
- update BIOS before serious testing;
- boot at **Auto/JEDEC** first;
- do not enable EXPO until baseline stability is established;
- leaving the kit at conservative Auto/JEDEC settings is acceptable because the kit is temporary.

Procurement preference is **PC Garage first, eMAG second**. The exact Phase-1 memory SKU remains provisional in the purchase-time sense: if stock disappears or a materially cheaper compatible kit appears at PC Garage/eMAG, substitute it rather than overpaying for temporary RAM.

### Eventual 256 GB

The endpoint remains **4×64 GB or equivalent**, but the exact purchase is deferred.

At upgrade time:

1. install the then-current stable ProArt BIOS;
2. re-check ASUS QVL for exact 64 GB modules and four-DIMM support;
3. prefer **4×64 GB ECC UDIMM** only if exact parts are available, credible and stable;
4. otherwise select a strongly validated **4×64 GB non-ECC UDIMM** configuration;
5. start at JEDEC/Auto settings and accept 5200 MT/s or lower if required for stability;
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

Clearance with the selected parts:

- cooler stock height: **168 mm**;
- Kingston `KF560C30BBEK2-32` module height: **34.9 mm**;
- normal dual-fan RAM clearance is roughly **32 mm**, so the front fan needs only about **3 mm** of lift;
- resulting practical cooler height is about **171 mm**;
- Fractal North XL Mesh CPU-cooler limit is **185 mm**;
- remaining margin is therefore about **14 mm**.

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

Phase-1 architecture:

- line-interactive;
- pure sine-wave output on battery;
- active-PFC compatible;
- approximately **1600 VA / 1000 W**;
- AVR;
- USB monitoring / graceful shutdown;
- user-replaceable battery.

Current provisional target: **CyberPower CP1600EPFCLCD**.

The UPS is deliberately sized for the current RTX 3060 workstation rather than the hypothetical future 600 W GPU. Reassess at the GPU upgrade.

## Remaining promotion / purchase-time gates

### Memory

- re-check PC Garage first and eMAG second immediately before purchase;
- verify exact SKU and seller/warranty;
- boot at JEDEC/Auto before considering EXPO.

### CPU cooler

The exact model is selected. Purchase-time work is limited to procurement sanity checks:

- prefer PC Garage first, eMAG second;
- confirm the listing is **standard NH-D15 G2**, not LBC or HBC;
- do not pay a material premium for LBC;
- install using the **-7 mm AM5 offset** position;
- raise the front fan only as much as required to clear the 34.9 mm Kingston DIMMs.

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

- verify Romanian warranty, replacement-battery availability and graceful-shutdown integration;
- confirm measured post-build wall power remains comfortably below 1000 W.

### SSD

The exact system SSD is selected. Immediately before purchase/install:

- confirm no new unresolved 990 PRO firmware/health issue;
- prefer PC Garage over eMAG when the price difference is small;
- confirm normal warranty and bare `MZ-V9P2T0BW` SKU;
- update/record firmware at bring-up.

## Final compatibility checks

Before purchase/assembly, verify:

- 9950X3D support on shipping ProArt BIOS or have USB BIOS FlashBack ready;
- selected Phase-1 RAM compatibility and stable Auto/JEDEC operation;
- standard NH-D15 G2 installed with 7 mm AM5 offset and minimal front-fan lift;
- selected 990 PRO firmware/warranty and `M.2_3` placement;
- Seasonic exact ATX 3.1 revision and native 12V-2x6 cable;
- RTX 3060 fit and future-GPU physical/cable clearance;
- North XL front-I/O headers against ProArt;
- rear NF-A14x25 G2 PWM on a controllable 4-pin fan header;
- UPS output wattage/waveform versus measured system load.

## Bring-up and validation

- update BIOS before serious memory tuning/testing;
- baseline boot at conservative/default memory settings;
- extended memory stability testing;
- if ECC memory is ever installed, validate actual ECC event reporting;
- update Samsung 990 PRO firmware, record SMART baseline and perform sustained-I/O temperature testing;
- sustained CPU thermal/load testing with NH-D15 G2;
- combined CPU/GPU thermal validation with the selected four-fan case layout;
- tune front/rear fan curves for sustained workloads rather than transient Ryzen spikes;
- inspect PSU/GPU power connectors for full insertion and strain-free routing;
- sleep/resume, WSL2 and virtualization validation;
- 10 GbE driver/firmware and sleep/resume validation;
- UPS communication and graceful-shutdown testing.
