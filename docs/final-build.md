# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, 256 GB architectural memory target, 32 GB Phase-1 memory floor, high-end air-cooling architecture, staged storage architecture, 1200 W ATX 3.1 PSU architecture, Fractal Design North XL Mesh chassis and existing GPU are selected**. Other rows remain intentionally open or may be tracked as provisional targets while dependent validation is still incomplete.

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
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Provisional target** | Leads on explicit 4×64 GB / 256 GB and ECC firmware evidence. **ASRock X870 Taichi Creator remains a live challenger** and may replace it if the exact 256 GB ECC memory review validates equally well. |
| Memory | **32 GB minimum Phase 1 / 256 GB architectural target** | **Target selected** | Phase-1 RAM is temporary commissioning memory. Preserve a validated 256 GB endpoint and assume the Phase-1 kit will be replaced rather than expanded into it. |
| CPU cooler | **Noctua NH-D15 G2 LBC** | **Provisional target** | High-end air cooling architecture selected. Standard NH-D15 G2 is fallback if materially cheaper/easier to source. |
| Storage | **2 TB system/tools NVMe now + 4 TB-or-larger work/VM NVMe later** | **Architecture selected** | Initial SSD should be mature TLC + DRAM PCIe 4.0. Reserve CPU-connected M.2_1 for the later work drive. |
| PSU | **Seasonic VERTEX GX-1200 ATX 3.1** | **Provisional target** | 1200 W ATX 3.1 / PCIe 5.1 architecture selected. Require native 12V-2x6 and verify exact revision at purchase. |
| Case | **Fractal Design North XL Mesh** | **Selected** | 413 mm GPU clearance, 185 mm CPU-cooler clearance, front + PSU filtration, 3×140 mm PWM front fans included, 290 mm PSU clearance, top 360 mm AIO fallback support. |
| Case fans | **3×140 mm front intake + 1×140 mm rear exhaust** | **Layout selected** | Use the three included front PWM fans; add one quality 140 mm PWM rear exhaust. No top/side fans initially. Noctua NF-A14x25 G2 PWM is provisional premium rear-fan target. |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially; preserve future upgrade path to one very high-end/high-VRAM GPU |
| UPS | — | Open | |
| OS | — | Open | |

## Current implementation strategy

### Memory

- Phase 1 may start at **32 GB**.
- 2×16 GB is preferred when similarly priced; 1×32 GB is acceptable if materially cheaper.
- Treat temporary RAM as replaceable.
- Long-term endpoint remains a separately validated **256 GB** configuration.

### Cooling

- Use high-end air cooling at stock/conservative CPU settings.
- Current provisional cooler: **Noctua NH-D15 G2 LBC**.
- Do not enable PBO/uncapped CPU power merely to exploit cooling headroom.
- A top-mounted 360 mm AIO remains fallback only; 420 mm radiator support is not required.

### Storage

- Buy one permanent **2 TB Gen4 TLC + DRAM** system/tools SSD initially.
- Later add a **4 TB-or-larger** work/VM/container/data SSD.
- Prefer M.2_3/M2_3 for the system drive and CPU-connected M.2_1/M2_1 for the future work drive.
- No RAID; external/network backup remains required.

### PSU

- Permanent architecture: **1200 W ATX 3.1 / PCIe 5.1**, native **12V-2x6**.
- Current provisional target: **Seasonic VERTEX GX-1200 ATX 3.1**.
- Verify current ATX 3.1 revision, warranty and native cable at purchase.

### Chassis and airflow

Selected chassis: **Fractal Design North XL Mesh**.

Selected initial fan layout:

- front: 3× included 140 mm PWM intake;
- rear: 1× added 140 mm PWM exhaust;
- top: empty;
- side: empty.

The intent is a direct front-to-rear path with mild positive pressure, good filtration and minimal fan count. Add top/side fans only if measured CPU/GPU/SSD/VRM thermals justify them.

North XL provides enough room for the current architecture without moving to an oversized full tower. Future GPU purchase must still validate card length, width, 12V-2x6 connector placement and side-panel cable-bend clearance.

## Motherboard promotion gate

Before the motherboard is promoted to **Selected**, verify:

- official and credible exact 256 GB path;
- stable expected 4×64 GB or equivalent operation at conservative settings;
- ECC implementation and OS-visible reporting if ECC is selected;
- current BIOS/AGESA maturity;
- purchase-time cost/value between ProArt and Taichi Creator.

## Cooler promotion gate

Before the NH-D15 G2 LBC is promoted to **Selected**, verify:

- motherboard compatibility;
- Phase-1 and eventual RAM height/clearance;
- fit within North XL's 185 mm cooler-height envelope, including any front-fan raising;
- current LBC availability and price premium versus standard NH-D15 G2.

## Final compatibility checks

Before purchase/assembly, verify:

- Ryzen 9 9950X3D / motherboard shipping BIOS compatibility;
- selected Phase-1 RAM compatibility;
- eventual 256 GB path and ECC behavior;
- NH-D15 G2 motherboard/RAM/North XL clearance;
- selected 2 TB SSD firmware/warranty;
- M.2 topology and lane-sharing behavior;
- Seasonic exact ATX 3.1 revision and native 12V-2x6 cable;
- current RTX 3060 fit;
- future-GPU length/width/power-cable clearance against North XL;
- North XL front-I/O headers versus selected motherboard;
- fan-header/control plan;
- UPS output wattage/waveform versus final system load.

## Bring-up and validation

- baseline boot at conservative/default memory settings;
- BIOS/firmware updates before memory tuning;
- extended memory stability testing;
- SSD firmware/SMART baseline and sustained-I/O temperature testing;
- sustained CPU thermal/load testing;
- combined CPU/GPU thermal validation with the selected four-fan case layout;
- tune fan curves for sustained workloads rather than transient Ryzen spikes;
- verify mild positive pressure and inspect dust accumulation after initial use;
- inspect PSU/GPU power connectors for full insertion and strain-free routing;
- sleep/resume, WSL2 and virtualization validation;
- 10 GbE driver/firmware and sleep/resume validation if used;
- UPS communication and graceful-shutdown testing.
