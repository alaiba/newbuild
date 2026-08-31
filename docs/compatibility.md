# Compatibility and Topology Tracker

This document captures cross-component constraints after the 2026-08-31 simplification pass.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- **128 GB = 2×64 GB DDR5 UDIMM / 1DPC**;
- **Thermalright Phantom Spirit 120 standard**;
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- existing RTX 3060 12 GB reused for as long as practical;
- no multi-GPU requirement;
- no UPS requirement.

Open:

- exact motherboard;
- exact 2×64 GB memory kit and ECC verdict;
- exact system and active-work storage devices;
- exact premium 750/850 W PSU;
- exact plug-in surge protector.

## Motherboard ↔ case

The selected chassis constrains the motherboard to **ATX or smaller**.

Motherboard selection must therefore not assume E-ATX. This is not a compromise for the actual workload; the previous E-ATX/Creator-class headroom was driven by requirements that have since been removed.

## Motherboard ↔ memory

Requirements:

- 128 GB total;
- two 64 GB UDIMMs;
- one DIMM per channel;
- normally A2/B2;
- Auto/JEDEC baseline;
- extended stability testing.

No 256 GB/four-DIMM requirement. ECC remains optional and matters only if exact-module support plus OS-visible error reporting are credible.

## Cooler ↔ memory ↔ case

Selected cooler/case:

- Thermalright **Phantom Spirit 120 standard**;
- cooler height approximately **157 mm**;
- Pure Base 501 CPU-cooler limit approximately **178 mm**;
- nominal vertical margin approximately **21 mm** before any front-fan adjustment.

Validate the final 2×64 GB kit for:

- DIMM height and front-fan interference;
- any required fan lift remaining inside the case limit;
- motherboard VRM/I/O-heatsink clearance;
- first PCIe/GPU-slot clearance.

The selected combination deliberately provides more physical tolerance than the previous NH-D15 G2 + regular-North concept.

## Case ↔ GPU

Pure Base 501 GPU-length envelope is approximately **368 mm** in the normal layout.

Policy:

- current RTX 3060 must fit trivially;
- do not reserve chassis volume for an unknown future 500–600 W flagship;
- if a future GPU genuinely exceeds the selected case envelope, reconsider the case at that future upgrade rather than oversizing today.

## Case airflow

Initial layout:

- **front:** one included 140 mm PWM intake;
- **rear:** one included 140 mm PWM exhaust;
- **additional fans:** none initially.

Add another front intake only if closed-case validation shows a useful improvement in CPU/GPU/VRM/SSD temperature or acoustics.

## Storage topology

### Hard requirement

At least one **CPU-direct M.2 x4** connection must be available for the active-work SSD without reducing the primary GPU link.

### System drive

Target ~1 TB. A second M.2 slot is desirable but **not mandatory**. A SATA SSD is an acceptable system-drive fallback if that enables a materially better motherboard/value choice.

### Active-work drive

- 1 TB sufficient;
- 2 TB preferred when price/value is attractive;
- Gen4 TLC preferred;
- CPU-direct x4 mandatory;
- Gen5 not required.

### Bulk/cold storage

May later use spare M.2, SATA SSD/HDD, external storage or NAS. The selected case preserves practical 3.5-inch HDD support. Old HDD reuse is acceptable for inactive data after health checks; never as the only copy of important data.

No RAID requirement.

## GPU / PCIe

- Reuse RTX 3060 12 GB.
- Do not preserve dual-GPU/x8+x8 capability as a requirement.
- When a future GPU replacement becomes worthwhile, retire the 3060.
- Preserve one normal full-performance primary GPU slot.

## Networking

- internet <1 Gb/s;
- LAN throughput irrelevant;
- **1 GbE sufficient**;
- 2.5 GbE a bonus;
- 5/10 GbE not worth a motherboard premium.

## VRM / CPU power delivery

The 9950X3D will run stock/conservatively. Require stable power delivery and good VRM thermals; do not value extreme phase counts, LN2/OC controls or excessive current capacity.

## PSU

Current target:

- premium **750 W** or **850 W** ATX 3.1;
- 750 W fully acceptable as baseline;
- 850 W only when premium is modest or exact model is materially better;
- no speculative 1000–1200 W requirement.

## UPS / surge protection

- no UPS initially;
- point-of-use surge-protected plug/power strip selected as practical protection;
- no electrical-installation changes required by the project.

## Windows / firmware

Selected:

- Windows 11 Pro x64;
- Windows 11 25H2 GA initial baseline;
- WSL2 + Ubuntu 26.04.1 LTS;
- UEFI native, Secure Boot, TPM 2.0/fTPM, SVM and IOMMU;
- CPU/RAM conservative during commissioning;
- BitLocker after firmware/driver stabilization.

## Provider dependencies

Provider grouping is not final until motherboard, RAM, SSDs and PSU are selected.

Still-valid procurement principles:

- maximum three providers overall;
- default target two hardware providers;
- software may use a separate provider when price/provenance justify it;
- exact SKU/revision and warranty clarity outrank small savings.
