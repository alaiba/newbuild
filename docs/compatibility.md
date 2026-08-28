# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. Except for reuse of the existing RTX 3060 12 GB, all component choices remain open. Therefore this tracker records **questions and dependencies**, not assumed configurations.

## CPU/platform ↔ motherboard

Determine together:

- socket/platform longevity and maturity
- chipset capabilities actually needed by the workload
- CPU power delivery requirements
- PCIe lane budget and generation
- USB/high-speed I/O requirements
- virtualization/IOMMU behavior
- firmware/BIOS quality and support history

No CPU platform or motherboard is selected yet.

## Motherboard ↔ memory

Resolve:

- required memory capacity
- DIMM topology for that capacity
- supported data rates at the chosen capacity/topology
- QVL/support evidence
- ECC availability and whether ECC is genuinely observable/correcting on the selected platform
- upgrade path versus initial configuration

The previously discussed 128 GB / 2×64 GB / DDR5-5600 configuration is a research hypothesis, not a constraint.

## Motherboard ↔ storage

The final topology should provide enough bandwidth and usable slots for the storage architecture that is ultimately selected while preserving:

- full-performance primary GPU operation where practical
- acceptable high-speed external I/O behavior
- useful future PCIe expansion
- sensible thermals and serviceability

Drive count and capacity remain open.

## Motherboard ↔ GPU / expansion

- Existing RTX 3060 12 GB will be used initially.
- Chassis, PSU and PCIe layout should avoid unnecessarily constraining a substantially larger future GPU.
- Motherboard evaluation must identify slot-width, lane-sharing and physical-clearance limitations for secondary PCIe devices.

## CPU ↔ cooling

Cooling selection follows the CPU/platform decision.

Evaluate:

- sustained thermal load
- acceptable acoustic target
- air versus liquid trade-offs
- socket/mount compatibility
- RAM/case clearance
- serviceability and long-term failure modes

No cooler architecture or model is selected yet.

## Storage ↔ workload

Determine whether the workload benefits materially from:

- one versus multiple physical SSDs
- OS/workload separation
- dedicated VM/container storage
- TLC versus other NAND classes
- DRAM-equipped versus DRAM-less designs
- PCIe 4.0 versus PCIe 5.0

Do not assume a 2 TB + 4 TB split until this is evaluated.

## PSU ↔ CPU / GPU / expansion

PSU wattage must be derived from:

- selected CPU/platform
- current RTX 3060 load
- plausible future GPU class
- storage and expansion devices
- transient requirements
- efficiency/noise goals

Do not assume 1000 W in advance.

## Case ↔ cooling / GPU / motherboard

Case selection must validate:

- selected cooler clearance
- present RTX 3060 fit
- sensible headroom for a future large GPU
- motherboard form factor
- airflow path and restriction
- dust filtration
- front-I/O compatibility
- maintainable fan/filter access over a 7–10 year lifespan

## UPS ↔ PSU / full system

UPS selection must follow a realistic system power model. Evaluate:

- output wattage, not VA alone
- waveform compatibility with the chosen PSU
- AVR / line-interactive / other topology trade-offs
- USB monitoring and graceful shutdown
- runtime at current-system load
- whether the UPS should also accommodate a future higher-power GPU

No UPS capacity or model is selected yet.
