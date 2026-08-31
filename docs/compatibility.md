# Compatibility and Topology Tracker

This document captures cross-component constraints for the selected workstation.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- ASUS **ProArt X870E-Creator WiFi**;
- Phase-1 **64 GB Crucial `CT2K32G56C46U5`**;
- long-term **256 GB** target, expected 4×64 GB.

Operating policy:

- current stable BIOS before serious validation;
- CPU stock/conservative;
- RAM Auto/JEDEC during commissioning;
- preserve the board's validated 256 GB path;
- ECC only if exact long-term modules, four-DIMM stability and OS-visible reporting are credible.

## Motherboard ↔ memory

Selected Phase-1 RAM:

- Crucial `CT2K32G56C46U5`;
- 64 GB / 2×32;
- DDR5-5600 CL46;
- 1.1 V;
- desktop UDIMM.

Strict purchase gate: reject `CT2K32G56C46S5` laptop/SO-DIMM.

Kingston `KF556C36BBEK2-64` remains the explicit-ProArt fallback if its price premium shrinks materially or Crucial availability deteriorates.

Install A2/B2, boot Auto/JEDEC first and run extended memory testing.

## Cooling ↔ memory ↔ case

Selected:

- Noctua NH-D15 G2 standard;
- included 7 mm AM5 offset;
- Fractal North XL Mesh `FD-C-NOR1X-01`.

Relevant envelope:

- NH-D15 G2 stock height ~168 mm;
- North XL cooler limit ~185 mm;
- selected Crucial DIMMs are low profile.

Expect zero or only minimal front-fan lift with ample case margin.

## Storage topology

Selected system SSD:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW`;
- install under the motherboard heatsink in **`M.2_3`**.

Reserve:

- **`M.2_1`** for future 4 TB+ work/VM/container/data SSD;
- avoid `M.2_2` unless its graphics/PCIe sharing trade-off is deliberately accepted.

This is why a PCIe 5 system-drive upgrade such as 9100 PRO is not attractive: the selected system slot is PCIe 4 and the useful CPU-connected Gen5 slot is intentionally reserved for the future work drive.

## Windows / WSL storage policy

- Windows-native source/caches stay on Windows-native storage.
- Linux-native high-I/O repos, package caches and container data stay inside WSL rather than `/mnt/c` where performance matters.
- Reassess WSL VHDX/container placement and a Windows Dev Drive when the future work SSD is added.
- BitLocker is enabled only after initial firmware/driver stabilization.

## GPU / expansion

- Reuse RTX 3060 12 GB initially.
- Preserve a future single high-power/high-VRAM GPU path.
- North XL airflow, 1200 W PSU architecture and storage topology all preserve that path.
- Recheck future GPU dimensions and 12V-2x6 bend clearance when the GPU is selected.

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

- prefer **VERTEX PX-1200 current ATX 3.1** when it is in stock and costs **≤~200 lei more** than the equivalent current GX;
- do not delay the build while PX is unavailable.

For either model:

- box/listing must say ATX 3.1;
- PCIe 5.1;
- supplied GPU cable must be current 12V-2x6;
- reject explicit old ATX 3.0 / 12VHPWR stock;
- use only Seasonic-approved modular cables.

The 160 mm VERTEX chassis fits comfortably inside North XL.

## UPS ↔ full system

Selected exact UPS:

**CyberPower PR1500ELCD**

- 1500 VA / **1350 W**;
- line-interactive;
- pure sine wave;
- Active-PFC compatible;
- Double Boost + Single Buck AVR;
- ~4 ms transfer;
- hot-swappable `RBP0023` battery;
- USB/PowerPanel Business;
- 8× IEC C13 outlets.

This replaces the former 1000 W CP1600 selection.

Compatibility rationale:

- current RTX 3060 machine is expected around ~450–550 W worst-case artificial wall load;
- future design case remains ~900–980 W;
- PR1500 places that future load at ~67–73% of its 1350 W rating instead of ~90–98% on the old 1000 W UPS;
- therefore it is likely to remain useful through the future GPU upgrade rather than becoming a Phase-1-only device.

Use correctly rated IEC cabling and validate USB graceful shutdown with a controlled mains-loss test.

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

## Windows license ↔ provider consolidation

Selected license channel: **Retail/FPP**.

Preferred procurement SKU:

- **`HAV-00197`**, Windows 11 Pro Retail/FPP USB Romanian package from EvoMAG.

Windows 11 Pro can add/switch display languages, so use English as the Windows display language after installation if desired. The package language does not justify a third provider when the rights/edition are otherwise equivalent.

Fallback: English Retail/FPP `HAV-00163` if the consolidated SKU is unavailable or materially overpriced.

## Provider dependencies

Default target: **two providers**.

### EvoMAG

CPU, motherboard, RAM, cooler, SSD, case, rear fan, PR1500ELCD and Windows FPP.

### Altex

Explicit-current Seasonic VERTEX PSU.

A third provider requires roughly **≥300 lei net saving** or materially better stock, exact-SKU/revision certainty or warranty.

If EvoMAG can explicitly verify its Seasonic as current ATX 3.1 / PCIe 5.1 / 12V-2x6, a one-provider order is acceptable.
