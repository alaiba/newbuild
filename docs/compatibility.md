# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

## Motherboard ↔ memory

- Target: 128 GB using 2×64 GB DDR5 DIMMs.
- Exact memory kit must be checked against the selected motherboard's current QVL and BIOS support.
- DDR5-5600 is the working target, but stability takes precedence over nominal speed.
- ECC support must be resolved before motherboard selection is closed.

## Motherboard ↔ storage

The selected motherboard must provide a lane topology that allows:

- one 2 TB system NVMe drive
- one 4 TB VM/work NVMe drive
- full-performance primary GPU operation
- acceptable USB4/high-speed I/O behavior
- reasonable future expansion without unexpected lane sharing

Exact M.2 slot placement will be documented once the motherboard is selected.

## Motherboard ↔ GPU / expansion

- Existing RTX 3060 12 GB will be used initially.
- Chassis, PSU and PCIe layout should preserve the option for a substantially larger future GPU.
- The motherboard review must identify any slot-width, lane-sharing or physical-clearance limitations for secondary PCIe cards.

## CPU ↔ cooling

- Ryzen 9 9950X is the current CPU candidate.
- Noctua NH-D15 G2 is the current cooling candidate.
- Review must verify sustained all-core behavior, thermal limits, socket mounting and RAM/case clearance.

## PSU ↔ future GPU

- Current RTX 3060 does not require a 1000 W PSU.
- A 1000 W ATX 3.1 PSU is being considered specifically to avoid replacing the PSU when moving to a future high-power/high-VRAM GPU.
- Native modern GPU power connectors and transient handling matter more than nominal wattage alone.

## Case ↔ cooling / GPU / storage

Case selection must validate:

- NH-D15 G2 height clearance
- future large GPU length and thickness
- adequate front-to-back airflow
- dust filtration
- front I/O compatibility with the motherboard
- maintainable fan/filter access over a 7–10 year lifespan

## UPS ↔ PSU / future GPU

UPS selection must be based on actual watt output, not VA rating alone. Preferred characteristics:

- line-interactive topology
- AVR
- pure sine-wave output preferred
- USB monitoring / graceful shutdown support
- enough watt capacity for the present system with margin
- decide explicitly whether it should also cover a future high-power GPU configuration
