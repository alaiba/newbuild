# Compatibility and Topology Tracker

This document captures cross-component constraints for the workstation after the memory-architecture change on 2026-08-31.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- final memory capacity **128 GB from day one**;
- final memory topology **2×64 GB DDR5 UDIMM / 1DPC**.

Reopened:

- exact motherboard;
- exact 2×64 GB memory kit;
- ECC/non-ECC verdict.

The ASUS ProArt X870E-Creator WiFi remains the incumbent reference until the next optimization pass, but its previous 4×64/256 GB-specific justification no longer controls the selection.

## Motherboard ↔ memory

Final constraints:

- 128 GB total;
- exactly two 64 GB UDIMMs as the intended configuration;
- one DIMM per channel;
- normally A2/B2, subject to the selected motherboard manual;
- Auto/JEDEC first;
- no EXPO/XMP requirement for baseline operation;
- extended memory stability testing before commissioning.

There is **no provisional 64 GB stage** and no planned 256 GB / four-DIMM upgrade.

ECC is optional. Select it only if exact-module board support and practical OS-visible reporting are credible.

## Cooling ↔ memory ↔ case

Selected:

- Noctua NH-D15 G2 standard;
- included 7 mm AM5 offset;
- Fractal North XL Mesh `FD-C-NOR1X-01`.

The exact 2×64 GB kit should prefer low-profile modules where practical. The North XL provides substantial cooler-height margin, so a small front-fan lift is acceptable but should not be required merely for decorative heat spreaders.

## Storage topology — incumbent pending review

Current plan:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as system/tools SSD;
- separate 4 TB-or-larger work/VM/container/data SSD later;
- no RAID;
- external/network backup required.

Under the incumbent ProArt topology:

- `M.2_3`: 990 PRO system/tools drive;
- `M.2_1`: reserved for future work SSD;
- avoid `M.2_2` unless its graphics/PCIe sharing trade-off is deliberately accepted.

The user requested a storage-architecture review before the motherboard/RAM optimization. Therefore these slot assignments are **incumbent assumptions**, not constraints to carry blindly into a different motherboard choice.

## Windows / WSL storage policy

- Windows-native source/caches stay on Windows-native storage.
- Linux-native high-I/O repos, package caches and container data stay inside WSL where performance matters.
- Reassess WSL VHDX/container placement and a Windows Dev Drive when storage architecture is finalized.
- BitLocker is enabled only after initial firmware/driver stabilization.

## GPU / expansion

- Reuse RTX 3060 12 GB initially.
- Preserve a future single high-power/high-VRAM GPU path.
- Recheck future GPU dimensions and 12V-2x6 bend clearance when that GPU is selected.

## Case / airflow

Selected:

- Fractal North XL Mesh `FD-C-NOR1X-01`;
- 3× included 140 mm front intake;
- 1× Noctua NF-A14x25 G2 PWM rear exhaust;
- top/side empty initially.

## PSU ↔ future GPU / UPS

Selected PSU architecture:

- **1200 W ATX 3.1 / PCIe 5.1 / 12V-2x6**.

Purchase baseline:

- Seasonic **VERTEX GX-1200 current ATX 3.1**.

Conditional value upgrade:

- prefer **VERTEX PX-1200 current ATX 3.1** when in stock at ≤~200 lei premium over equivalent GX;
- do not delay the build while PX is unavailable.

## UPS ↔ full system

Selected exact UPS:

**CyberPower PR1500ELCD**

- 1500 VA / 1350 W;
- line-interactive pure sine wave;
- Active-PFC compatible;
- AVR;
- hot-swappable battery;
- USB/PowerPanel Business.

The UPS is intended to remain useful through the future high-power GPU upgrade rather than being a temporary Phase-1 device.

## Windows ↔ firmware / security

Selected:

- Windows 11 Pro x64;
- initial Windows 11 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS.

Firmware baseline:

- UEFI native;
- CSM disabled;
- Secure Boot;
- TPM 2.0 / AMD fTPM;
- SVM;
- IOMMU unless a real stability problem appears;
- CPU/RAM conservative during commissioning.

Do the planned BIOS update before enabling BitLocker.

## Windows license

Selected license channel: **Retail/FPP**.

Current purchase target:

- **`HAV-00163`**, Windows 11 Pro Retail/FPP USB English from PROstore.

Windows is allowed to use a separate software provider because its long-term warranty/RMA burden is negligible relative to hardware.

## Provider dependencies

The previous purchase total/provider grouping is **not final** until motherboard, exact 2×64 GB RAM and storage architecture are re-optimized.

Still-valid procurement principles:

- maximum three providers overall;
- default target two hardware providers;
- software can use a separate provider when price/provenance justify it;
- exact SKU/revision and warranty clarity outrank small nominal savings.
