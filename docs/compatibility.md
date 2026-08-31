# Compatibility and Topology Tracker

This document captures cross-component constraints after the memory, storage, networking, power and cooling simplifications finalized on 2026-08-31.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- **128 GB from day one**;
- **2×64 GB DDR5 UDIMM / 1DPC**;
- high-quality air-cooling architecture;
- existing RTX 3060 reused for as long as practical;
- no multi-GPU requirement;
- no UPS requirement.

Open:

- exact CPU cooler;
- exact motherboard;
- exact 2×64 GB memory kit and ECC verdict;
- exact system and active-work storage devices;
- exact premium 750/850 W PSU;
- final case reconfirmation.

## Motherboard ↔ memory

Requirements:

- 128 GB total;
- two 64 GB UDIMMs;
- one DIMM per channel;
- normally A2/B2;
- Auto/JEDEC baseline;
- extended stability testing.

No 256 GB/four-DIMM requirement.

ECC is optional and matters only if exact-module support plus OS-visible error reporting are credible.

## Cooling ↔ memory ↔ case

Air cooling remains selected, but **the exact cooler is reopened**.

The previous NH-D15 G2 lock must not constrain the final RAM or case unnecessarily.

Evaluate the final cooler/RAM/case combination for:

- total cooler height including any front-fan lift;
- DIMM height and fan interference;
- motherboard VRM/I/O-heatsink clearance;
- first PCIe/GPU-slot clearance;
- case side-panel clearance;
- sustained 9950X3D thermals and acoustics at stock/conservative settings.

Reference candidates include Phantom Spirit 120-class, Noctua NH-U12A and NH-D15 G2. Prefer the least bulky/least expensive option that meets the real thermal/acoustic/serviceability requirement.

The Fractal North XL remains selected for now but gets one final size/value review. A smaller case is allowed if the final cooler/RAM/GPU combination fits comfortably.

## Storage topology

### Hard requirement

At least one **CPU-direct M.2 x4** connection must be available for the active-work SSD without reducing the primary GPU link.

### System drive

Target ~1 TB. A second M.2 slot is desirable but **not mandatory**. A SATA SSD is an acceptable system-drive fallback if that enables a materially better motherboard/value choice.

### Active-work drive

- 1 TB sufficient;
- 2 TB preferred when the price increment is attractive;
- Gen4 TLC preferred;
- CPU-direct x4 mandatory;
- Gen5 not required.

### Bulk/cold storage

May later use spare M.2, SATA SSD/HDD, external storage or NAS. Old HDD reuse is acceptable for inactive data after health checks; never as the only copy of important data.

No RAID requirement.

## GPU / PCIe

- Reuse RTX 3060 12 GB.
- Do not preserve dual-GPU/x8+x8 capability as a requirement.
- When a future GPU replacement becomes worthwhile, retire the 3060.
- Do not pre-size motherboard/PSU around a hypothetical 500–600 W flagship.
- Preserve one normal full-performance primary GPU slot.

## Networking

Actual network needs are modest:

- internet <1 Gb/s;
- local-network throughput irrelevant;
- **1 GbE sufficient**;
- 2.5 GbE a bonus;
- 5/10 GbE not worth a motherboard premium.

## VRM / CPU power delivery

The 9950X3D will run stock/conservatively.

Require:

- stable power delivery;
- good VRM thermal behavior;
- quality components.

Do not value:

- extreme phase counts for their own sake;
- LN2/OC controls;
- excessive current capacity intended for extreme overclocking.

## PSU

The previous 1200 W architecture is superseded.

Current target:

- premium **750 W** or **850 W** ATX 3.1;
- 750 W fully acceptable as the baseline;
- 850 W only when the premium is modest or the model is materially better;
- no speculative 1000–1200 W requirement.

## UPS / surge protection

- no UPS in the initial BOM;
- point-of-use surge-protected plug/power strip selected as the practical protection measure;
- no electrical-installation changes required by the project;
- point-of-use protection relies on proper protective earth and does not equal coordinated building-level SPD protection.

## Windows / firmware

Selected:

- Windows 11 Pro x64;
- initial Windows 11 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS;
- UEFI native;
- Secure Boot;
- TPM 2.0 / AMD fTPM;
- SVM;
- IOMMU unless a real stability issue appears;
- CPU/RAM conservative during commissioning;
- BitLocker after firmware/driver stabilization.

## Provider dependencies

Provider grouping is not final until cooler/case, motherboard, RAM, SSDs and PSU are selected.

Still-valid procurement principles:

- maximum three providers overall;
- default target two hardware providers;
- software can use a separate provider when price/provenance justify it;
- exact SKU/revision and warranty clarity outrank small savings.
