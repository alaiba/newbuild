# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform, 256 GB memory-capacity target and existing GPU are selected**. Other rows remain intentionally open or may be tracked as provisional targets while dependent validation is still incomplete.

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
| Motherboard | — | Open | Next decision will nominate a **provisional target**; final selection requires 256 GB memory/ECC/topology/firmware validation |
| Memory | 256 GB target | **Target selected** | Exact topology/kit/data rate/ECC undecided; scale back only if 256 GB cost or stability/performance trade-off is disproportionate |
| CPU cooler | — | Open | Must suit sustained Ryzen 9 9950X3D development workloads; air vs liquid undecided |
| Storage | — | Open | Capacity, drive count and layout undecided |
| PSU | — | Open | Wattage/model undecided |
| Case | — | Open | |
| Case fans | — | Open | Depends on case/thermal design |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially |
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

## Final compatibility checks

Before purchase/assembly, verify the checks appropriate to the selected architecture, including:

- Ryzen 9 9950X3D / AM5 motherboard compatibility and shipping firmware support
- official motherboard support for 256 GB
- exact 4×64 GB or other selected 256 GB memory configuration support at the intended data rate
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
- extended 256 GB memory stability testing
- verification of memory error reporting where supported
- sustained CPU thermal/load testing
- SSD firmware/health checks and sustained I/O testing
- GPU load testing
- sleep/resume and WSL2/virtualization validation
- UPS communication and graceful shutdown testing
