# Compatibility and Topology Tracker

This document captures cross-component constraints for the workstation after the memory and storage architecture changes on 2026-08-31.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- final memory capacity **128 GB from day one**;
- final memory topology **2×64 GB DDR5 UDIMM / 1DPC**;
- initial storage topology **~1 TB system NVMe + 1–2 TB active-work NVMe**, with bulk/cold storage added later only when needed.

Reopened:

- exact motherboard;
- exact 2×64 GB memory kit;
- ECC/non-ECC verdict;
- exact system SSD;
- exact 1 TB/2 TB active-work SSD.

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

The exact 2×64 GB kit should prefer low-profile modules where practical. The North XL provides substantial cooler-height margin.

## Storage topology — final requirements

Initial storage consists of two physical internal NVMe SSDs:

- **~1 TB system/tools SSD**;
- **1–2 TB active-work SSD**.

Motherboard requirements:

1. at least two M.2 x4 slots must be usable simultaneously;
2. prefer one **CPU-direct x4** slot for the active-work SSD;
3. a **chipset-connected x4** slot is fully acceptable for the system SSD;
4. using the selected pair must **not reduce the primary GPU from x16**;
5. integrated M.2 heatsinks are preferred;
6. at least one practical later bulk-storage path through extra M.2 and/or SATA is desirable;
7. extra Gen5/high-speed M.2 capacity is not worth a large motherboard premium by itself.

Do not assume slot labels across vendors. Lane-sharing behavior must be checked in the selected board manual.

### System SSD

The system SSD does not require flagship bandwidth or a CPU-direct connection.

Priorities:

- reputable vendor;
- mature firmware;
- normal warranty;
- enough capacity headroom;
- good price;
- TLC preferred where cost-effective;
- Gen3/Gen4 performance is sufficient.

A chipset M.2 x4 path is expected to be effectively transparent for its Windows/tools role.

### Active-work SSD

The active-work SSD receives storage-performance and endurance priority.

Capacity policy:

- **1 TB is sufficient**;
- **2 TB is preferred only when its incremental cost is attractive**;
- do not buy 4 TB merely to retain inactive data on the performance tier.

Prefer:

- TLC NAND;
- DRAM-equipped design where reasonably priced;
- strong sustained/mixed behavior;
- mature firmware;
- sensible endurance/warranty;
- CPU-direct x4 connection where available without compromising GPU lanes.

**Gen4 is sufficient. Gen5 is not a motherboard-selection requirement.**

### Storage role separation

Keep latency-sensitive active data on the active-work SSD where supported:

- current Git repositories;
- Maven/Gradle caches and build outputs;
- WSL2 VHDX and Linux-native working data;
- containers;
- active Android SDK/AVDs;
- active VMs;
- local databases;
- current datasets/games/models where appropriate.

Keep Windows, applications, page file/crash-dump infrastructure and ordinary user-profile data on the system SSD.

Move archived/infrequently accessed data to bulk/cold storage when necessary rather than oversizing the active-work SSD.

### Bulk/cold storage

Later storage may use:

- spare chipset-connected M.2;
- SATA SSD;
- SATA HDD;
- external/NAS storage.

Existing older HDDs are acceptable for infrequently accessed data after SMART/health checks. They must not hold the only copy of important data.

No RAID is required. External/network/cloud backup remains required for important data.

## Windows / WSL storage policy

- Linux-native high-I/O repos, package caches and container data should remain inside the WSL filesystem rather than `/mnt/c` where performance matters.
- Place WSL VHDX/container stores on the active-work SSD using supported relocation mechanisms.
- Windows-native project/cache locations may also use the active-work SSD when applications support explicit paths.
- BitLocker is enabled only after initial firmware/driver/storage validation.

## GPU / expansion

- Reuse RTX 3060 12 GB initially.
- Preserve a future single high-power/high-VRAM GPU path.
- The selected two-M.2 configuration must preserve the main GPU at x16.
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

## Provider dependencies

The previous purchase total/provider grouping is **not final** until motherboard, exact 2×64 GB RAM and exact two SSDs are optimized.

Still-valid procurement principles:

- maximum three providers overall;
- default target two hardware providers;
- software can use a separate provider when price/provenance justify it;
- exact SKU/revision and warranty clarity outrank small nominal savings.
