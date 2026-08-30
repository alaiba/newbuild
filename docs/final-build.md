# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, 256 GB architectural memory target, 32 GB Phase-1 memory floor, high-end air-cooling architecture, staged storage architecture, 1200 W ATX 3.1 PSU architecture and existing GPU are selected**. Other rows remain intentionally open or may be tracked as provisional targets while dependent validation is still incomplete.

## Status vocabulary for this document

- **Selected** — closed decision; use as a fixed input to subsequent component selection unless explicitly reopened.
- **Target selected** — design target is fixed, but implementation details remain open.
- **Provisional target** — preferred current candidate, intentionally not final; may change if dependent validation fails.
- **Open** — no preferred model/configuration has been nominated yet.

A motherboard should remain **Provisional target** until the exact 256 GB memory path, ECC verdict, PCIe/storage topology, future high-end-GPU path and firmware maturity have been validated sufficiently to justify purchase.

## Selected components

| Component | Selected model | Status | Notes |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | AM5 platform; fixed input for subsequent component selection |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Provisional target** | Leads on explicit 4×64 GB / 256 GB and ECC firmware evidence. **ASRock X870 Taichi Creator remains a live challenger** and may replace it if the exact 256 GB ECC memory review validates equally well; ASRock has cleaner PCIe/storage topology, stronger diagnostics and materially lower current cost. |
| Memory | **32 GB minimum Phase 1 / 256 GB architectural target** | **Target selected** | Phase-1 RAM is temporary commissioning memory. Any stable 32 GB-or-larger configuration is acceptable; 2×16 GB is preferred when similarly priced, but 1×32 GB is acceptable. Preserve a validated 256 GB endpoint and assume the Phase-1 kit will be replaced rather than expanded into it. |
| CPU cooler | **Noctua NH-D15 G2 LBC** | **Provisional target** | **High-end air cooling architecture selected.** LBC is the preferred AM5-specific target; standard NH-D15 G2 with AM5 offset mount is the fallback if materially cheaper/easier to source. ARCTIC Liquid Freezer III Pro 360 remains a liquid fallback only if real sustained workload validation exposes inadequate thermal/acoustic margin. |
| Storage | **2 TB system/tools NVMe now + 4 TB-or-larger work/VM NVMe later** | **Architecture selected** | Initial SSD should be a mature high-quality TLC + DRAM PCIe 4.0 drive. Exact 2 TB model remains price/firmware-dependent. Reserve the clean CPU-connected M.2_1 slot for the later work drive; Gen5 is deferred until that purchase and only if then justified. |
| PSU | **Seasonic VERTEX GX-1200 ATX 3.1** | **Provisional target** | **1200 W ATX 3.1 / PCIe 5.1 architecture selected** for the future 600 W-class single-GPU design case. Require native 12V-2x6. Verify the exact current ATX 3.1 revision at purchase because older VERTEX stock used ATX 3.0 / 12VHPWR under very similar naming. VERTEX PX-1200 is the premium alternative if the price delta becomes small. |
| Case | — | Open | Airflow-first strategy selected; must clear the 168 mm NH-D15 G2 and provide comfortable future GPU + 12V-2x6 cable clearance. Top-mounted 360 mm AIO support is useful fallback headroom; 420 mm radiator support is no longer a requirement. |
| Case fans | — | Open | Depends on final case/thermal design; prefer large standard replaceable fans |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially; preserve future upgrade path to one very high-end/high-VRAM GPU |
| UPS | — | Open | |
| OS | — | Open | |

## Motherboard promotion gate

Before a provisional motherboard target is promoted to **Selected**, verify:

- official support for 256 GB;
- a credible exact 256 GB DIMM path, preferably with QVL/vendor evidence;
- stable expected 4×64 GB or equivalent operation at conservative settings;
- ECC implementation and OS-visible error reporting if ECC is selected;
- PCIe/M.2 lane-sharing behavior against the intended storage and future high-end-GPU configuration;
- physical layout for a future large/high-power GPU;
- mature BIOS/AGESA support and useful recovery/serviceability features; and
- current cost/value versus the closest credible alternatives.

The current comparison is intentionally still **ProArt X870E-Creator vs X870 Taichi Creator**, not a closed ASUS purchase decision.

## Memory purchase strategy

The first build does **not** need to buy 256 GB immediately.

- **32 GB** is the selected Phase-1 floor.
- **2×16 GB** is preferred when similarly priced because it preserves dual-channel bandwidth.
- **1×32 GB** or any other stable 32 GB-or-larger configuration is acceptable when it is the cheapest sensible commissioning option.
- Larger temporary capacities are optional only when the price increment is attractive.
- The motherboard/platform must still preserve a credible **256 GB** path.
- Do not rely on adding more DIMMs to the Phase-1 kit later; when upgrading to 256 GB, reassess the best matched and validated configuration available at that time.

This makes Phase-1 memory the preferred budget-release valve while protecting the parts of the build that are harder or more expensive to replace later.

## Cooling strategy

The selected architecture is **high-end air cooling operated at stock/conservative CPU settings**.

Current provisional target:

- **Noctua NH-D15 G2 LBC**

Fallbacks:

- standard **NH-D15 G2** with the included 7 mm AM5 offset mount if the LBC variant carries an unreasonable sourcing/price premium;
- **ARCTIC Liquid Freezer III Pro 360** only if real sustained development workloads later demonstrate a material thermal/acoustic reason to use liquid cooling.

Do not enable PBO/uncapped CPU power merely to exploit cooling headroom. The headroom exists to reduce temperature/noise and improve environmental margin.

420 mm radiator support is **not** a chassis-selection gate. If liquid cooling is later justified, prefer a top-mounted 360 mm configuration that preserves unobstructed front intake for the future GPU path.

## Cooler promotion gate

Before the NH-D15 G2 LBC is promoted from provisional to **Selected**, verify:

- exact motherboard compatibility;
- exact Phase-1 and eventual 256 GB RAM height/clearance;
- case CPU-cooler clearance, including any required front-fan raising;
- current Romanian/EU LBC availability and premium versus standard NH-D15 G2;
- no new 9950X3D-specific evidence indicates unacceptable sustained behavior at stock/conservative power.

## Storage strategy

The selected long-term storage structure is deliberately staged:

### Phase 1

- buy **one permanent 2 TB system/tools SSD**;
- prefer high-quality **TLC + DRAM, PCIe 4.0 x4**;
- do not pay a large Gen5 premium merely for headline sequential speed.

### Later work-drive expansion

Add a **4 TB-or-larger work/VM/container/data SSD** when capacity pressure or price/value justifies it.

The work drive should host the write-heavy/project-oriented workloads such as:

- source trees and build outputs;
- Maven/Gradle caches;
- WSL2/Docker data;
- Android SDK/emulators;
- VMs;
- local databases;
- scratch/data-processing workloads.

At that later purchase, reassess whether PCIe 5.0 has become worthwhile. The architecture preserves the option without paying for it now.

### Preferred M.2 assignment

For either current motherboard finalist:

- **M.2_3 / M2_3 chipset Gen4 x4:** 2 TB system/tools drive;
- **M.2_1 / M2_1 CPU-connected slot:** future 4 TB+ work drive.

On the ProArt this avoids `M.2_2`, which would reduce the primary GPU lane allocation. On the Taichi Creator it leaves `M2_2` free and avoids its USB4-sharing trade-off.

No RAID is required. This two-drive layout is for workload/recovery separation, **not backup**.

### Initial SSD shortlist

Exact SKU remains provisional and should be rechecked immediately before purchase. Current serious 2 TB Gen4 candidates are:

- Samsung 990 PRO;
- WD Black SN850X;
- Seagate FireCuda 530R;
- Crucial T500.

Choose using current firmware/health history, full Romanian/EU warranty and price before chasing small benchmark differences.

## PSU strategy

The selected permanent PSU architecture is:

- **1200 W**;
- **ATX 3.1 / PCIe 5.1**;
- native **12V-2x6** for a future 600 W-class GPU;
- fully modular;
- strong transient handling and complete electrical protections;
- long warranty and credible independent electrical testing.

Current provisional target:

- **Seasonic VERTEX GX-1200 ATX 3.1**

Why 1200 W:

- 1000 W is sufficient for the present RTX 3060 and many future GPUs, but is intentionally too tight for the explicit design envelope of a 600 W future accelerator plus stock/conservative 9950X3D and full platform load;
- 1200 W provides useful sustained thermal/acoustic/aging margin without moving into an excessive PSU class;
- 1300–1600 W is unnecessary for the intended single-GPU AM5 architecture.

The VERTEX GX currently leads on value because it combines the selected architecture with a 12-year current manufacturer warranty and competitive Romanian pricing. The **VERTEX PX-1200 ATX 3.1** is the premium efficiency/noise alternative; choose it instead only if its purchase-time premium is modest.

### PSU promotion gate

Before promoting the exact PSU to **Selected**:

- verify the unit/box is the current **ATX 3.1 / 12V-2x6** revision rather than older ATX 3.0 inventory;
- verify full Romanian/EU warranty path;
- refresh VERTEX GX/PX and credible 1200 W competitor pricing;
- verify case clearance and future GPU 12V-2x6 routing/bend space;
- use only the PSU's compatible native modular cables.

## Final compatibility checks

Before purchase/assembly, verify the checks appropriate to the selected architecture, including:

- Ryzen 9 9950X3D / AM5 motherboard compatibility and shipping firmware support
- official motherboard support for 256 GB
- compatibility of the selected Phase-1 memory kit
- exact 4×64 GB or other eventual 256 GB memory configuration support at the intended data rate
- QVL/vendor evidence and current BIOS maturity for high-density DIMMs
- **NH-D15 G2 motherboard/RAM/case clearance, including raised-front-fan height if needed**
- selected 2 TB SSD firmware, warranty and fit under the motherboard M.2_3 heatsink
- M.2_3/M2_3 system-drive assignment and preservation of M.2_1/M2_1 for the future work drive
- storage lane-sharing behavior
- GPU physical clearance and primary-slot bandwidth
- **PSU exact ATX 3.1 revision, native 12V-2x6 support and manufacturer warranty**
- **future GPU power-cable routing and connector bend clearance**
- case front-I/O headers versus motherboard headers
- fan/header count and control
- UPS output wattage and waveform versus measured/estimated system load

## Bring-up and validation

A detailed validation plan will be added before assembly. It should include, as applicable:

- baseline boot at conservative/default memory settings
- BIOS/firmware updates before memory tuning
- extended memory stability testing at the installed Phase-1 capacity
- extended 256 GB memory stability testing when/if the system is upgraded to that capacity
- verification of memory error reporting where supported
- sustained CPU thermal/load testing at stock/conservative CPU settings
- tune CPU-fan curves using sustained workloads rather than transient Ryzen temperature spikes
- **SSD firmware update/verification before loading important data**
- SMART/health baseline recording
- sustained SSD I/O and temperature/throttling testing
- GPU load testing
- combined CPU/GPU thermal validation of the final case fan layout
- inspect PSU/GPU power connectors for full insertion and strain-free routing
- sleep/resume and WSL2/virtualization validation
- 10 GbE driver/firmware and sleep/resume validation if onboard 10 GbE is used
- UPS communication and graceful shutdown testing
