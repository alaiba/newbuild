# Compatibility and Topology Tracker

This document captures cross-component constraints that should not be evaluated in isolation.

The build is greenfield. The existing RTX 3060 12 GB is reused initially; the CPU, motherboard, **64 GB Phase-1 memory capacity**, chassis, cooling architecture, exact CPU cooler, storage architecture, exact initial system SSD, exact PSU, rear exhaust fan, Phase-1 UPS, **Windows 11 Pro host OS and WSL2 Linux environment** are selected.

## CPU/platform ↔ motherboard

Selected:

- **AMD Ryzen 9 9950X3D**
- **ASUS ProArt X870E-Creator WiFi**

Operating policy:

- use current stable BIOS before serious validation;
- keep CPU at stock/conservative power settings;
- preserve the board's validated 256 GB memory path;
- use USB BIOS FlashBack if the shipping BIOS is unsuitable for the CPU.

## Motherboard ↔ memory

Long-term architectural target:

- credible path to **256 GB**, expected 4×64 GB;
- exact long-term DIMMs deferred;
- ECC UDIMM preferred only if exact modules, four-DIMM stability and OS-visible ECC behavior are credible.

Selected Phase-1 capacity:

- **64 GB (2×32 GB)**.

Preferred exact target:

- **Crucial `CT2K32G56C46U5`**;
- DDR5-5600 CL46;
- 1.1 V;
- ordinary unbuffered desktop UDIMMs;
- low-profile bare modules.

Compatibility fallback:

- **Kingston `KF556C36BBEK2-64`**, explicitly listed by Kingston for the ProArt X870E-Creator WiFi.

Bring-up policy:

- install A2/B2;
- boot at Auto/JEDEC first;
- do not enable EXPO/XMP during baseline validation;
- prioritize stability over headline timings;
- run extended memory testing.

## CPU ↔ cooling

Selected:

- **Noctua NH-D15 G2 standard base**
- included **7 mm AM5 offset mount**
- CPU at stock/conservative settings.

The **ASUS ProArt X870E-Creator WiFi is explicitly listed as compatible by Noctua**.

## Cooling ↔ memory ↔ case

Relevant envelope:

- NH-D15 G2 stock height: **168 mm**;
- normal dual-fan RAM clearance: approximately **32 mm**;
- North XL CPU-cooler limit: **185 mm**.

Selected Crucial 64 GB kit:

- low-profile bare modules around the low-30-mm height class;
- expect zero or only minimal front-fan lift;
- even a small lift leaves ample side-panel margin.

Kingston fallback:

- ~34.9 mm module height;
- ~3 mm front-fan lift;
- ~171 mm practical cooler height;
- ~14 mm case margin.

## Motherboard ↔ storage

Selected initial SSD:

- **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`**
- permanent system/tools role
- PCIe 4.0 x4, bare M.2 2280 drive under the motherboard heatsink.

Preferred ProArt topology:

- **`M.2_3`**: Samsung 990 PRO 2 TB system/tools SSD
- **`M.2_1`**: future 4 TB-or-larger work/VM/container/data SSD
- keep **`M.2_2`** unused unless its graphics-lane trade-off is intentionally accepted
- **`M.2_4`** remains available for later lower-priority storage.

## Storage ↔ Windows / WSL

Initial system disk:

- Windows 11 Pro uses the 990 PRO as the UEFI/GPT system disk;
- do not carve the initial 2 TB SSD into a complicated permanent partition scheme merely to create a Dev Drive;
- BitLocker is enabled only after the first firmware/driver baseline is stable.

Filesystem policy:

- Windows-native repositories/build caches stay on Windows-native storage;
- Linux-native repositories, package caches and container data stay inside the WSL2 filesystem when I/O is significant;
- avoid using `/mnt/c` as the default location for Linux-native high-I/O builds merely for convenience;
- when the future 4 TB+ work SSD is added, reassess moving WSL VHDX/container/cache data there;
- also evaluate a Windows ReFS Dev Drive on the future work SSD for Windows-native source/caches if measured workload performance justifies it.

Microsoft documents Dev Drive as available across Windows 11 editions, so this storage strategy does **not** require Windows 11 Pro for Workstations.

## Motherboard ↔ GPU / expansion

- Existing RTX 3060 12 GB is reused initially.
- North XL Mesh, the selected 1200 W PSU and air cooling preserve a path to a substantially larger future high-VRAM GPU.
- The storage topology avoids `M.2_2`, preserving the primary GPU path.
- CPU-connected x8/x8 remains useful future headroom but is not a current requirement.

## Case ↔ cooling / GPU / motherboard

Selected chassis:

- **Fractal Design North XL Mesh**

Selected airflow:

- 3×140 mm included front intake;
- 1× Noctua NF-A14x25 G2 PWM rear exhaust;
- no top/side fans initially.

The front remains unobstructed by a radiator, preserving clean future-GPU intake.

## PSU ↔ CPU / GPU / case

Selected exact PSU:

- **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision**.

Compatibility points:

- 1200 W provides the selected margin for a future ~600 W single GPU plus the 9950X3D platform;
- ProArt motherboard/dual CPU EPS requirements are covered without adapters;
- 160 mm PSU body fits easily inside the North XL;
- future high-power GPU uses the Seasonic-supplied 12V-2x6 cable;
- future GPU width and connector bend radius must be revalidated when that GPU is selected.

Purchase/receipt acceptance:

- box/listing says ATX 3.1;
- GPU cable is 12V-2x6;
- reject old ATX 3.0 / 12VHPWR inventory;
- retain serial/model/warranty evidence;
- use only Seasonic-approved modular cables.

## Windows ↔ firmware / security

Selected host:

- **Windows 11 Pro x64**;
- initial installation: **Windows 11 25H2 General Availability**.

Required firmware baseline:

- UEFI-native boot;
- CSM disabled;
- Secure Boot enabled;
- TPM 2.0 / AMD fTPM enabled;
- AMD SVM enabled;
- IOMMU enabled unless a demonstrated stability issue appears;
- CPU/memory conservative during commissioning.

Do the first planned BIOS update before enabling BitLocker. After the firmware baseline is stable, enable BitLocker and retain its recovery key somewhere independent of this workstation.

Do not use Insider or preview Windows builds for the workstation baseline.

## Windows ↔ virtualization / Android / Linux

Selected Linux environment:

- **WSL2 + Ubuntu 26.04.1 LTS**.

Windows 11 Pro is selected rather than Home because it preserves full Hyper-V host capability and Remote Desktop hosting in addition to WSL2.

Virtualization policy:

- WSL2 for normal Linux CLI/dev/container workflows;
- Android Emulator uses the supported Windows hypervisor path;
- Hyper-V VMs only when a genuinely separate VM boundary is useful;
- no native Linux dual boot unless a later workload demonstrates a bare-metal Linux requirement.

The selected 64 GB Phase-1 memory provides useful concurrency headroom for IDE + WSL2 + emulator + moderate VM/container workloads. The eventual 256 GB configuration substantially expands that envelope.

## Windows ↔ NVIDIA GPU

Default Windows GPU driver branch:

- **current NVIDIA Studio Driver WHQL**.

This matches the stability-first workstation policy while retaining gaming support. Switch to Game Ready only for a specific game that materially needs day-zero optimizations/fixes.

If future local-AI tooling is installed, validate CUDA visibility and driver/toolkit compatibility as a separate acceptance test.

## Windows edition ↔ hardware scale

Standard **Windows 11 Pro** is sufficient.

Do not buy Pro for Workstations merely because this is a powerful PC:

- one CPU socket is far below its 4-CPU scale feature;
- 256 GB target RAM is far below its 6 TB memory scale;
- no current SMB Direct/RDMA requirement;
- Windows Dev Drive does not require Pro for Workstations.

## UPS ↔ PSU / full system

Selected Phase-1 UPS:

- **CyberPower CP1600EPFCLCD**
- 1600 VA / 1000 W
- line-interactive pure sine wave
- Active-PFC compatible
- AVR
- USB HID / PowerPanel
- user-replaceable `RBP0142` battery.

The UPS is intentionally sized for the current RTX 3060 system, not the PSU's 1200 W nameplate. Reassess when a materially higher-power GPU is installed or measured wall load approaches roughly 700–800 W.

Under Windows, connect the UPS by USB and validate actual automatic graceful shutdown with a controlled mains-loss test.

## Procurement dependencies

For purchase-ready parts:

- **PC Garage and Altex are co-preferred Romanian retailers**;
- **eMAG is also acceptable**;
- exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order;
- small price differences do not matter;
- material price differences may justify another reputable seller.

For Phase-1 memory:

- target Crucial `CT2K32G56C46U5` around the current ~4.7–4.8k lei market class;
- compare Kingston `KF556C36BBEK2-64` if Crucial availability/warranty/pricing degrades materially.

For Windows:

- official Microsoft Store Romania price control is **1,199 RON** for Windows 11 Pro if a new license is required;
- reuse an existing legitimate transferable Pro license if available;
- avoid grey-market activation keys as part of the baseline build.
