# Compatibility and Topology Tracker

This document captures the current cross-component constraints for the workstation.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- ASUS **TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- Crucial **`CT2K64G56C46U5`**, 128 GB = 2×64 GB DDR5-5600 / 1DPC / non-ECC;
- Thermalright **Phantom Spirit 120 standard**;
- be quiet! **Pure Base 501 Airflow Black `BG074`**;
- Crucial **T710 2 TB `CT2000T710SSD8`** primary NVMe;
- existing RTX 3060 12 GB;
- no multi-GPU requirement;
- no UPS requirement.

Open:

- exact premium 750/850 W PSU;
- exact plug-in surge protector.

## Motherboard ↔ memory

Final configuration:

- two 64 GB UDIMMs in **A2/B2**;
- one DIMM per channel;
- native JEDEC DDR5-5600 / 1.1 V kit;
- Auto/JEDEC baseline;
- no EXPO/XMP requirement;
- extended stability testing.

The CPU and board support ECC UDIMM, but the final kit is non-ECC because practical 64 GB ECC UDIMM availability is poor. **RDIMM is incompatible with AM5.**

The board supports 256 GB total memory and ASUS exposes 2×64 GB / DDR5-5600 support categories. The exact Crucial kit remains subject to normal commissioning validation rather than assuming QVL coverage from category support alone.

## Cooler ↔ memory ↔ case

- Phantom Spirit 120 height: ~157 mm;
- Pure Base 501 CPU-cooler limit: ~178 mm;
- nominal vertical margin: ~21 mm;
- Crucial modules are low-profile.

This combination provides comfortable physical tolerance. At assembly, still verify front-fan position, DIMM clearance, motherboard heatsinks and first GPU-slot clearance before final cable management.

## Motherboard ↔ storage ↔ GPU

Selected topology:

```text
Ryzen 9 9950X3D
├── primary PCIe 5.0 x16 -> RTX 3060
├── M.2_1 CPU 5.0 x4     -> Crucial T710 2 TB primary NVMe
└── M.2_2 CPU 4.0 x4     -> empty / future expansion

B650 chipset
├── M.2_3 PCIe 4.0 x4    -> empty / future expansion
├── second full-length slot -> PCIe 4.0 x1 only
├── 4 × SATA             -> existing/later cold storage
└── normal platform I/O
```

Using `M.2_1` for the T710 does not require reducing the primary GPU link.

The selected board does not provide a meaningful secondary x4 expansion path. This is accepted because no add-in high-speed NIC, HBA, capture card or second GPU is required.

### Primary SSD

- exact model: **Crucial T710 2 TB `CT2000T710SSD8`**;
- preferred/selected slot: `M.2_1`;
- CPU-direct PCIe 5.0 x4;
- TLC + DRAM-equipped design;
- install bare/non-heatsink model under the motherboard M.2 heatsink;
- holds Windows, applications and active development/work data together.

Current storage use is approximately **600 GB**, so 2 TB is expected to provide substantial headroom. No second NVMe is required initially.

### Bulk/cold storage

Use existing healthy SATA SSD/HDD devices where suitable for archives, old projects, inactive VMs, installers, media and similar infrequently accessed data. Validate SMART/health first and never rely on an old drive as the sole copy of important information.

`M.2_2` and `M.2_3` remain available for additive future storage.

No RAID, SSD cache layer or automatic tiering requirement.

## Case ↔ GPU

Pure Base 501 GPU-length envelope is approximately **368 mm** in the normal layout.

- current RTX 3060 fits easily;
- no chassis volume is reserved for an unknown 500–600 W future flagship;
- if a future replacement exceeds the envelope, revisit the case at that time.

## Case airflow

Initial layout:

- front: one included 140 mm PWM intake;
- rear: one included 140 mm PWM exhaust;
- no additional fans initially.

Add another front intake only if closed-case validation shows a useful thermal/acoustic improvement.

## Networking

- internet <1 Gb/s;
- LAN throughput irrelevant;
- board's **2.5 GbE** is already more than required;
- 5/10 GbE carries no selection value.

## VRM / CPU operation

The 9950X3D runs stock/conservatively. The selected board uses 8+2+1 80 A stages and is specified for compatible AMD CPUs up to 200 W. This is sufficient engineering margin for the intended policy; do not value or enable extreme-overclocking behavior simply because electrical headroom exists.

## PSU

Current target:

- premium **750 W** or **850 W** ATX 3.1;
- 750 W baseline;
- 850 W only when premium is modest or exact model materially better;
- no speculative 1000–1200 W requirement.

## UPS / surge protection

- no UPS initially;
- use a point-of-use surge-protected Schuko plug/power strip;
- no electrical-installation changes required.

## Windows / firmware commissioning

- Windows 11 Pro x64, initial 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS;
- current stable production motherboard BIOS;
- UEFI, Secure Boot, TPM 2.0/fTPM, SVM, IOMMU;
- CPU stock/conservative;
- RAM Auto/JEDEC;
- update/record T710 firmware and validate SMART/temperature behavior;
- BitLocker after firmware/driver/storage stability is established.

## Provider dependencies

Motherboard, RAM and primary SSD exact models are closed, but supplier selection remains subject to live price/stock. The RAM market is especially volatile.

Provider principles remain:

- maximum three providers overall;
- target two hardware providers;
- exact SKU/revision and warranty clarity outrank small savings;
- software may use a separate provider where provenance/price justify it.
