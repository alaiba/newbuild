# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, 256 GB architectural memory target, 64 GB minimum initial memory floor and existing GPU are selected**. Other rows remain intentionally open or may be tracked as provisional targets while dependent validation is still incomplete.

## Status vocabulary for this document

- **Selected** — closed decision; use as a fixed input to subsequent component selection unless explicitly reopened.
- **Target selected** — design target is fixed, but implementation details remain open.
- **Provisional target** — preferred current candidate, intentionally not final; may change if dependent validation fails.
- **Open** — no preferred model/configuration has been nominated yet.

A motherboard should remain **Provisional target** until the exact 256 GB memory path, ECC verdict, PCIe/storage topology and firmware maturity have been validated sufficiently to justify purchase.

## Selected components

| Component | Selected model | Status | Notes |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | AM5 platform; fixed input for subsequent component selection |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Provisional target** | Leads on explicit 4×64 GB / 256 GB and ECC firmware evidence. **ASRock X870 Taichi Creator remains a live challenger** and may replace it if the exact 256 GB ECC memory review validates equally well; ASRock has cleaner PCIe/storage topology, stronger diagnostics and materially lower current cost. |
| Memory | **64 GB minimum initial / 256 GB architectural target** | **Target selected** | Minimum starting point is 2×32 GB. Exact initial kit may be 64, 96 or 128 GB depending current value. Preserve a validated 256 GB endpoint; treat the initial kit as replaceable rather than assuming it will later be combined with another kit. |
| CPU cooler | — | Open | Must suit sustained Ryzen 9 9950X3D development workloads; preserve both top-tier air and 360/420 mm AIO options until motherboard/RAM clearance is known. |
| Storage | — | Open | Capacity, drive count and layout undecided |
| PSU | — | Open | Wattage/model undecided; preserve headroom for a future high-power/high-VRAM GPU |
| Case | — | Open | Airflow-first strategy selected; current research shortlist remains open |
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

- **64 GB (2×32 GB)** is the selected minimum acceptable starting point.
- 96 GB (2×48 GB) or 128 GB (2×64 GB) may be selected if their current incremental cost is justified.
- The motherboard/platform must still preserve a credible **256 GB** path.
- Do not rely on adding a second independently purchased kit later; when upgrading to 256 GB, reassess the best matched and validated configuration available at that time.

This makes memory capacity the preferred budget-release valve while protecting the parts of the build that are harder or more expensive to replace later.

## Final compatibility checks

Before purchase/assembly, verify the checks appropriate to the selected architecture, including:

- Ryzen 9 9950X3D / AM5 motherboard compatibility and shipping firmware support
- official motherboard support for 256 GB
- compatibility of the selected initial two-DIMM memory kit
- exact 4×64 GB or other eventual 256 GB memory configuration support at the intended data rate
- QVL/vendor evidence and current BIOS maturity for high-density DIMMs
- cooler/socket/case/RAM clearance
- storage slot placement and lane-sharing behavior
- GPU physical clearance and primary-slot bandwidth
- PSU capacity and connector requirements for the selected system and plausible future GPU
- case front-I/O headers versus motherboard headers
- fan/header count and control
- UPS output wattage and waveform versus measured/estimated system load

## Bring-up and validation

A detailed validation plan will be added before assembly. It should include, as applicable:

- baseline boot at conservative/default memory settings
- BIOS/firmware updates before memory tuning
- extended memory stability testing at the installed initial capacity
- extended 256 GB memory stability testing when/if the system is upgraded to that capacity
- verification of memory error reporting where supported
- sustained CPU thermal/load testing
- SSD firmware/health checks and sustained I/O testing
- GPU load testing
- sleep/resume and WSL2/virtualization validation
- 10 GbE driver/firmware and sleep/resume validation if onboard 10 GbE is used
- UPS communication and graceful shutdown testing
