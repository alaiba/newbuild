# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, motherboard, 256 GB architectural memory target, 32 GB Phase-1 memory floor, high-end air-cooling architecture, staged storage architecture, 1200 W ATX 3.1 PSU architecture, Fractal Design North XL Mesh chassis, Phase-1 UPS architecture and existing GPU are selected**. Several purchase-time SKUs remain provisional.

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
| Memory | **KLEVV FIT V 32 GB (2×16) DDR5-5600 CL30 `KD5AGU880-56K300F`** | **Provisional Phase-1 purchase target** | Phase-1 RAM is temporary. Current ~2.39k lei target because it is among the cheaper reputable 2×16 desktop kits in the distorted Aug 2026 market. Boot at Auto/JEDEC first; EXPO is optional. Replace rather than expand when moving to the 256 GB endpoint. |
| Long-term memory | **256 GB architectural target, expected 4×64 GB** | **Target selected / purchase deferred** | Prefer ECC UDIMM only if exact 64 GB modules, four-DIMM support, stability and OS-visible ECC reporting are credible at upgrade time; otherwise use validated non-ECC. |
| CPU cooler | **Noctua NH-D15 G2 LBC** | **Provisional target** | High-end air cooling architecture selected. Standard NH-D15 G2 is fallback if materially cheaper/easier to source. |
| Storage | **2 TB system/tools NVMe now + 4 TB-or-larger work/VM NVMe later** | **Architecture selected** | Initial SSD should be mature TLC + DRAM PCIe 4.0. Reserve CPU-connected M.2_1 for the later work drive. |
| PSU | **Seasonic VERTEX GX-1200 ATX 3.1** | **Provisional target** | 1200 W ATX 3.1 / PCIe 5.1 architecture selected. Require native 12V-2x6 and verify exact revision at purchase. |
| Case | **Fractal Design North XL Mesh** | **Selected** | 413 mm GPU clearance, 185 mm CPU-cooler clearance, front + PSU filtration, 3×140 mm PWM front fans included, 290 mm PSU clearance, top 360 mm AIO fallback support. |
| Case fans | **3×140 mm front intake + 1×140 mm rear exhaust** | **Layout selected** | Use the three included front PWM fans; add one quality 140 mm PWM rear exhaust. No top/side fans initially. |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially; preserve future path to one very high-end/high-VRAM GPU |
| UPS | **CyberPower CP1600EPFCLCD** | **Provisional target** | Phase-1 architecture selected: line-interactive, pure sine, ~1600 VA / 1000 W. Reassess UPS capacity when a materially higher-power GPU is installed. |
| OS | — | Open | |

## Motherboard selection rationale

The ProArt is closed because its firmware history explicitly addresses four-64-GB / 256 GB operation, four-DIMM stability and ECC UDIMM behavior. The ASRock X870 Taichi Creator remains attractive on price/topology but did not match ASUS's exact validation evidence.

Detailed evidence: `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.

## Memory implementation strategy

### Phase 1

Current purchase target:

- **KLEVV FIT V 32 GB (2×16 GB) DDR5-5600 CL30 — `KD5AGU880-56K300F`**;
- current Romanian low offer observed around **2,390 lei** on 2026-08-31;
- use the motherboard-recommended two-DIMM slots;
- update BIOS before serious testing;
- boot at **Auto/JEDEC** first;
- do not enable EXPO until baseline stability is established;
- leaving the kit at conservative Auto/JEDEC settings is acceptable because the kit is temporary.

This exact SKU is provisional because current DDR5 prices are unusually distorted. If another reputable desktop 2×16 GB DDR5 kit is materially cheaper on order day, substitute it rather than paying a premium for the KLEVV model.

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

- high-end air cooling at stock/conservative CPU settings;
- provisional cooler: **Noctua NH-D15 G2 LBC**;
- standard NH-D15 G2 fallback;
- top-mounted 360 mm AIO remains fallback only;
- no PBO/uncapped power merely to exploit cooling headroom.

## Storage strategy

- buy one permanent **2 TB Gen4 TLC + DRAM** system/tools SSD initially;
- later add a **4 TB-or-larger** work/VM/container/data SSD;
- preferred ProArt assignment: `M.2_3` for system drive and CPU-connected `M.2_1` for the future work drive;
- avoid `M.2_2` unless its graphics-lane trade-off is intentionally accepted;
- no RAID; external/network backup remains required.

## PSU strategy

- permanent architecture: **1200 W ATX 3.1 / PCIe 5.1**, native **12V-2x6**;
- provisional target: **Seasonic VERTEX GX-1200 ATX 3.1**;
- verify current ATX 3.1 revision and native cable at purchase.

## Chassis and airflow

Selected chassis: **Fractal Design North XL Mesh**.

Initial fan layout:

- front: 3× included 140 mm PWM intake;
- rear: 1× added 140 mm PWM exhaust;
- top: empty;
- side: empty.

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

### Cooler

- verify exact Phase-1 RAM height/clearance;
- verify fit within North XL's 185 mm envelope including any front-fan raising;
- refresh LBC versus standard G2 pricing.

### PSU

- verify current ATX 3.1 / 12V-2x6 revision;
- verify warranty and case/cable routing.

### UPS

- verify Romanian warranty, replacement-battery availability and graceful-shutdown integration;
- confirm measured post-build wall power remains comfortably below 1000 W.

### SSD

- refresh firmware history, warranty and pricing immediately before purchase.

## Final compatibility checks

Before purchase/assembly, verify:

- 9950X3D support on shipping ProArt BIOS or have USB BIOS FlashBack ready;
- selected Phase-1 RAM compatibility and stable Auto/JEDEC operation;
- NH-D15 G2 / RAM / North XL clearance;
- selected SSD firmware/warranty and M.2 placement;
- Seasonic exact ATX 3.1 revision and native 12V-2x6 cable;
- RTX 3060 fit and future-GPU physical/cable clearance;
- North XL front-I/O headers against ProArt;
- fan-header/control plan;
- UPS output wattage/waveform versus measured system load.

## Bring-up and validation

- update BIOS before serious memory tuning/testing;
- baseline boot at conservative/default memory settings;
- extended memory stability testing;
- if ECC memory is ever installed, validate actual ECC event reporting;
- SSD firmware/SMART baseline and sustained-I/O temperature testing;
- sustained CPU thermal/load testing;
- combined CPU/GPU thermal validation with the selected four-fan case layout;
- tune fan curves for sustained workloads rather than transient Ryzen spikes;
- inspect PSU/GPU power connectors for full insertion and strain-free routing;
- sleep/resume, WSL2 and virtualization validation;
- 10 GbE driver/firmware and sleep/resume validation;
- UPS communication and graceful-shutdown testing.
