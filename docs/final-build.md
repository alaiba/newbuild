# Final Build

This is the current source-of-truth architecture for the workstation. Memory is finalized at **128 GB / 2×64 GB / 1DPC from day one**. Storage is finalized at the role/topology level as **~1 TB system NVMe + 1–2 TB active-work NVMe from day one, with bulk/cold storage added only when needed**. The exact motherboard, RAM kit and SSD models remain to be optimized before purchase.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | ASUS **ProArt X870E-Creator WiFi** incumbent reference | **Reopened for optimization** because 4×64/256 GB is no longer required |
| RAM capacity | **128 GB from day one** | **Selected / final** |
| RAM topology | **2×64 GB DDR5 UDIMM, 1DPC, A2/B2** | **Selected / final** |
| Exact RAM kit | Exact 2×64 GB matched kit | **Open for optimization** |
| ECC | ECC UDIMM only if end-to-end support/reporting is compelling | **Open within RAM optimization** |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset | **Selected** |
| System/tools SSD | **~1 TB NVMe**, reliability/capacity/value optimized; chipset-connected x4 acceptable | **Role/capacity selected; exact model open** |
| Active-work SSD | **1 TB sufficient; 2 TB preferred when current price/value justifies it**, Gen4 TLC preferred; CPU-direct x4 preferred | **Role selected; exact capacity/model open** |
| Bulk/cold storage | Add later only when needed; extra NVMe/SATA SSD/HDD acceptable according to workload | **Expansion policy selected** |
| Storage RAID | **No RAID**; external/network/cloud backup required for important data | **Selected** |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6** | **Selected baseline** |
| PSU value upgrade | **VERTEX PX-1200 current ATX 3.1** | **Preferred if in stock at ≤~200 lei premium** |
| Case | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected** |
| Rear fan | **Noctua NF-A14x25 G2 PWM**, standard square-frame single | **Selected** |
| Case airflow | 3× included 140 mm front intake + 1×140 mm rear exhaust | **Selected** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse / selected** |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **Selected** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Memory architecture — final

Initial assembly uses the intended lifetime memory configuration:

**128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel.**

This permanently supersedes temporary 64 GB memory and the planned 256 GB / 4×64 GB endpoint.

The exact 2×64 GB SKU remains open for the motherboard/RAM optimization. Bring-up remains conservative: current stable BIOS, A2/B2, Auto/JEDEC first, no EXPO/XMP during baseline validation, extended memory testing.

## Storage architecture — final

Initial assembly uses two independent internal NVMe SSDs:

- **~1 TB system/tools SSD** for Windows, applications, IDE/tool binaries, page file, servicing and ordinary profile data;
- **1–2 TB active-work SSD** for current repositories, Maven/Gradle caches, WSL2/container data, active Android images, VMs, databases and other latency-sensitive working data.

### Active-work capacity rule

**1 TB is accepted as sufficient.**

Prefer **2 TB** only when the incremental price is modest enough that the additional headroom is good value. Do not buy 4 TB merely because total accumulated local data might eventually exceed 2 TB.

Infrequently accessed data moves to a later bulk/cold-storage tier instead.

### System SSD policy

The system drive is **not a performance prestige component**. With 128 GB RAM and active development data on a separate drive, a reputable mature Gen3/Gen4 NVMe is already sufficient. Optimize C: for reliability, capacity headroom, warranty and price. A chipset-connected x4 M.2 slot is fully acceptable.

### Active-work SSD policy

The active-work drive receives the performance/endurance priority. Prefer:

- CPU-direct x4 connection;
- TLC NAND;
- DRAM-equipped design where reasonably priced;
- good sustained/mixed behavior;
- mature firmware and sensible endurance.

**Gen4 is sufficient; Gen5 is a bonus only when its premium is negligible or a demonstrated workload benefits.**

### Bulk/cold storage

When capacity becomes an issue, add storage rather than replacing the initial SSDs.

Suitable later options include:

- another chipset-connected NVMe SSD;
- SATA SSD;
- SATA HDD;
- external/NAS storage where appropriate.

Existing old spinning disks may be reused for archived/infrequently accessed data after health/SMART checks. They must not become the only copy of important data.

No RAID is required.

The old Samsung 990 PRO 2 TB system-drive selection, fixed 4 TB work-drive requirement and staged storage plans are superseded. The 990 PRO may still compete if its current price makes sense for one of the final roles.

## Motherboard consequence

The ASUS ProArt X870E-Creator WiFi remains the incumbent technical reference, but it is no longer final.

With 128 GB / 1DPC and the simplified storage hierarchy, the motherboard can be re-optimized for stability, firmware quality, networking, PCIe/storage topology, serviceability, future high-power GPU support and value.

Storage requirements are:

1. at least two simultaneously usable M.2 x4 slots;
2. one preferably CPU-direct x4 for the active-work SSD;
3. one chipset x4 slot is sufficient for the ~1 TB system SSD;
4. using the two selected M.2 slots must not reduce the main GPU from x16;
5. a practical later bulk-storage path via extra M.2 and/or SATA is desirable;
6. Gen5 M.2 bandwidth and excessive high-speed storage slots should not command a material premium.

## Current price envelope

Previous complete-order totals are obsolete.

Do not publish a new purchase total until:

1. the exact 2×64 GB kit is selected;
2. the motherboard re-optimization is complete;
3. exact ~1 TB system SSD and 1 TB/2 TB active-work SSD are selected and priced.

## Hard purchase gates that remain valid

### CPU
- exact Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### RAM
- **128 GB total**;
- **2×64 GB matched DDR5 UDIMM kit**;
- 1DPC / A2+B2;
- no temporary 2×32 GB purchase.

### Storage
- two internal NVMe SSDs from day one;
- system drive target approximately 1 TB, reputable/mature/value-oriented;
- active-work drive 1 TB or 2 TB based on current value, high-quality TLC preferred;
- CPU-direct x4 preferred for active work; chipset x4 acceptable for system;
- no requirement for Gen5;
- selected two M.2 slots must preserve GPU x16;
- future bulk storage must be addable through M.2/SATA without replacing the initial pair;
- no RAID requirement.

### Cooler
- NH-D15 G2 **standard**;
- included AM5 offset mount;
- no LBC/HBC substitution.

### PSU
For GX or conditional PX:
- ATX 3.1;
- PCIe 5.1;
- current 12V-2x6 cable;
- reject explicit old ATX 3.0 / 12VHPWR stock.

### Case
- exact `FD-C-NOR1X-01` North XL Charcoal Black Mesh.

### UPS
- exact **CyberPower PR1500ELCD**;
- 1500 VA / 1350 W;
- new/sealed;
- correctly rated IEC cabling;
- USB graceful-shutdown validation.

### Windows
- Windows 11 Pro;
- **Retail/FPP**;
- current purchase target `HAV-00163` English USB from PROstore;
- not OEM/DSP or an undocumented activation key.

## OS / firmware baseline

- Windows 11 Pro 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS;
- NVIDIA Studio Driver WHQL baseline;
- current stable motherboard BIOS;
- UEFI, Secure Boot, TPM 2.0, SVM/IOMMU;
- RAM Auto/JEDEC during commissioning;
- CPU stock/conservative;
- BitLocker only after firmware/driver stabilization.

## Next decision sequence

1. Re-optimize **motherboard** for final 128 GB 1DPC and storage topology.
2. Select exact **2×64 GB RAM**, including ECC/non-ECC verdict.
3. Select exact **~1 TB system SSD + 1 TB/2 TB active-work SSD** using current Romanian price/value data.
4. Recalculate provider consolidation and purchase total.

Detailed decisions: `docs/decisions.md`.
