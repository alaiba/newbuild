# Final Build

This document will become the final bill of materials once component decisions are closed.

## Selected components

| Component | Selected model | Status | Notes |
|---|---|---|---|
| CPU | — | Pending | |
| Motherboard | — | Pending | |
| Memory | — | Pending | |
| CPU cooler | — | Pending | |
| System SSD | — | Pending | |
| Work / VM SSD | — | Pending | |
| PSU | — | Pending | |
| Case | — | Pending | |
| Case fans | — | Pending | |
| GPU | NVIDIA GeForce RTX 3060 12 GB | Existing / selected | Reuse initially |
| UPS | — | Pending | |
| OS | — | Pending | |

## Final compatibility checks

Before purchase/assembly, verify:

- CPU support with shipping BIOS
- exact 2×64 GB memory kit on motherboard QVL or otherwise supported with strong evidence
- cooler/socket/case/RAM clearance
- M.2 slot placement and lane-sharing behavior
- GPU physical clearance
- PSU connector requirements for current and plausible future GPU
- case front-I/O headers versus motherboard headers
- fan/header count and control
- UPS output wattage versus measured/estimated system load

## Bring-up and validation

A detailed validation plan will be added before assembly. It should include at least:

- baseline boot at JEDEC memory settings
- BIOS/firmware updates
- memory stability testing
- sustained CPU thermal/load testing
- SSD firmware/health checks and sustained I/O testing
- GPU load testing
- sleep/resume and WSL2/virtualization validation
- UPS communication and graceful shutdown testing
