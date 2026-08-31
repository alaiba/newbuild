# Compatibility and Topology Tracker

This document captures the current cross-component constraints for the workstation.

## Core platform

Selected:

- AMD Ryzen 9 **9950X3D**;
- ASUS **TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`**;
- Crucial **`CT2K64G56C46U5`**, 128 GB = 2×64 GB DDR5-5600 / 1DPC / non-ECC;
- Thermalright **Phantom Spirit 120 standard**;
- be quiet! **Pure Base 501 Airflow Black `BG074`**;
- existing RTX 3060 12 GB;
- no multi-GPU requirement;
- no UPS requirement.

Open:

- exact system and active-work SSDs;
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

## Cooler ↔ memory ↔ case

- Phantom Spirit 120 height: ~157 mm;
- Pure Base 501 CPU-cooler limit: ~178 mm;
- nominal vertical margin: ~21 mm;
- Crucial modules are low-profile.

This combination provides comfortable physical tolerance. At assembly, still verify front-fan position, DIMM clearance, motherboard heatsinks and first GPU-slot clearance before final cable management.

## Motherboard ↔ storage ↔ GPU

Preferred topology:

```text
Ryzen 9 9950X3D
├── primary PCIe x16  -> RTX 3060
├── M.2_1 CPU x4      -> active-work NVMe
└── M.2_2 CPU x4      -> system/tools NVMe

B850 chipset
├── M.2_3 PCIe 4 x4   -> optional future storage
├── 4 × SATA          -> later SSD/HDD storage
└── normal platform I/O
```

Using `M.2_1` and `M.2_2` does not require reducing the primary GPU link.

`M.2_3` shares resources with the secondary PCIe 4.0 x4 expansion path. If `M.2_3` is populated, that secondary slot may become unavailable. This is acceptable because no add-in NIC, HBA, capture card or second GPU is required.

### Active-work drive

- preferred slot: `M.2_1`;
- 1 TB sufficient;
- 2 TB when price/value is attractive;
- Gen4 TLC preferred;
- Gen5 not required even though the slot supports it.

### System drive

- preferred slot: `M.2_2`;
- target ~1 TB;
- NVMe is now preferred because the selected board provides the path without trade-off;
- SATA remains a fallback.

### Bulk/cold storage

May later use `M.2_3`, SATA SSD/HDD, external storage or NAS. Existing healthy HDDs are allowed for inactive data after health checks but never as the only copy of important data.

No RAID requirement.

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

The 9950X3D runs stock/conservatively. The selected board has sufficient power delivery; do not value or enable extreme-overclocking behavior simply because electrical headroom exists.

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
- BitLocker after firmware/driver/storage stability is established.

## Provider dependencies

Motherboard and RAM exact models are closed, but supplier selection remains subject to live price/stock. The RAM market is especially volatile.

Provider principles remain:

- maximum three providers overall;
- target two hardware providers;
- exact SKU/revision and warranty clarity outrank small savings;
- software may use a separate provider where provenance/price justify it.
