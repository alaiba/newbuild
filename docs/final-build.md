# Final Build

This document will become the final bill of materials once component decisions are closed.

At present, the **CPU/platform and existing GPU are selected**. Other rows remain intentionally open.

## Selected components

| Component | Selected model | Status | Notes |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | AM5 platform; fixed input for subsequent component selection |
| Motherboard | — | Open | Must be AM5; chipset/model still under review |
| Memory | — | Open | Capacity/topology/speed/ECC undecided within AM5 constraints |
| CPU cooler | — | Open | Must suit sustained Ryzen 9 9950X3D development workloads; air vs liquid undecided |
| Storage | — | Open | Capacity, drive count and layout undecided |
| PSU | — | Open | Wattage/model undecided |
| Case | — | Open | |
| Case fans | — | Open | Depends on case/thermal design |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially |
| UPS | — | Open | |
| OS | — | Open | |

## Final compatibility checks

Before purchase/assembly, verify the checks appropriate to the selected architecture, including:

- Ryzen 9 9950X3D / AM5 motherboard compatibility and shipping firmware support
- exact memory configuration support at the intended capacity and data rate
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
- BIOS/firmware updates
- memory stability testing
- sustained CPU thermal/load testing
- SSD firmware/health checks and sustained I/O testing
- GPU load testing
- sleep/resume and WSL2/virtualization validation
- UPS communication and graceful shutdown testing
