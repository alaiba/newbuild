# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | **ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`** | **Selected** |
| RAM | **Crucial `CT2K64G56C46U5` — 128 GB (2×64 GB) DDR5-5600 CL46, 1.1 V, non-ECC** | **Selected** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | **Selected** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** |
| Case airflow | **2× included 140 mm PWM: front intake + rear exhaust** | **Selected initial layout** |
| System storage | **~1 TB NVMe preferred**; SATA remains acceptable fallback | **Role/capacity selected; exact model open** |
| Active-work SSD | **1 TB sufficient; 2 TB if price/value is attractive**, Gen4 TLC preferred; CPU-direct x4 | **Role selected; exact model open** |
| Bulk/cold storage | Add later only when needed via spare NVMe/SATA SSD/HDD/external/NAS | **Expansion policy selected** |
| Storage RAID | **No RAID** | **Selected** |
| PSU | **Premium 750 W or 850 W ATX 3.1** | **Reopened; exact model open** |
| UPS | **None initially** | **Selected** |
| Point-of-use surge protection | Reputable plug-in surge protector / protected power strip | **Selected policy; exact model open** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse for as long as useful/reliable** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Motherboard — final

Selected board: **ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`**.

It wins because it satisfies the actual workstation requirements without Creator/X870E premiums:

- ATX, fitting the Pure Base 501;
- mature Ryzen 9 9950X3D firmware path;
- official high-capacity DDR5 support and continuing memory-stability firmware work;
- CPU-connected primary PCIe x16 graphics path;
- **M.2_1 CPU PCIe 5.0 x4** and **M.2_2 CPU PCIe 4.0 x4**, both useful without reducing the primary GPU link;
- third chipset M.2 for optional later expansion;
- four SATA ports;
- BIOS FlashBack and Q-LED CPU/DRAM/VGA/BOOT diagnostics;
- competent VRM for stock/conservative 9950X3D operation;
- 2.5 GbE, already beyond the actual network requirement.

The chipset-connected `M.2_3` shares resources with the secondary PCIe 4.0 x4 expansion slot. That is acceptable: the build has no planned add-in NIC, HBA, second GPU or other use that makes this secondary slot a requirement.

The previous ProArt/Taichi Creator analysis is superseded as a purchase decision. 10 GbE, CPU x8/x8, multiple Gen5 M.2 slots and extreme-overclocking power delivery are not value drivers.

## Memory — final

Selected kit:

> **Crucial `CT2K64G56C46U5` — 128 GB (2×64 GB), DDR5-5600 CL46, 1.1 V, non-ECC UDIMM.**

Reasons:

- exact lifetime capacity in one matched two-DIMM kit;
- electrically favorable **1DPC** topology;
- native **JEDEC DDR5-5600 at 1.1 V**, so no EXPO/XMP profile is needed to reach the intended operating rate;
- conservative timings/voltage match the stability-first objective;
- low-profile modules fit cleanly with the Phantom Spirit 120;
- independent Ryzen 9000/B850 evidence exists for the exact kit and native JEDEC operation.

### ECC verdict

The 9950X3D and selected ASUS board support ECC UDIMM, and ASUS continues ECC-specific firmware work. However, the fixed 128 GB / 2×64 GB target makes ECC impractical today: mainstream 64 GB ECC **UDIMM** availability is poor, while readily available 64 GB server modules are generally **RDIMM**, which AM5 cannot use.

Therefore the final configuration is **non-ECC**. Do not reduce capacity, move to four DIMMs or buy an RDIMM merely to obtain ECC.

### Bring-up policy

1. Install the two modules in **A2/B2**.
2. Update to a current stable production BIOS before full validation.
3. Boot at **Auto/JEDEC**.
4. Target the kit's native **DDR5-5600 / 1.1 V** behavior; do not enable EXPO/XMP during commissioning.
5. Run extended memory testing before the workstation is considered stable.
6. Record BIOS/AGESA, trained timings and voltages.
7. Do not raise memory/SoC voltage merely to improve benchmark numbers.

## Cooling and chassis — final

- **Thermalright Phantom Spirit 120 standard**;
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- initial case airflow: one included 140 mm front intake + one included 140 mm rear exhaust.

The cooler is ~157 mm high inside a ~178 mm case limit, leaving useful tolerance for DIMM/front-fan positioning. No additional case fan is purchased until measurements justify it.

## Storage architecture

The selected motherboard improves the storage topology beyond the minimum requirement:

- **M.2_1 CPU x4:** preferred active-work SSD location;
- **M.2_2 CPU x4:** natural system-drive location;
- **M.2_3 chipset x4:** optional future storage, at the cost of the otherwise non-required secondary PCIe x4 slot;
- **4× SATA:** later SSD/HDD bulk storage.

Therefore the ~1 TB system drive can normally remain NVMe; SATA is retained only as an allowed fallback, not the preferred topology.

Active work remains 1 TB sufficient / 2 TB when good value, with mature Gen4 TLC preferred. Gen5 is not required even though `M.2_1` can support it.

## GPU policy

Reuse the RTX 3060 for as long as useful/reliable. A future replacement retires it rather than creating a dual-GPU design. Do not distort motherboard, PSU or chassis choices around an unknown future flagship GPU.

## PSU architecture — open

Current target:

- premium **750 W ATX 3.1** as legitimate baseline;
- **850 W** only when an equally good model costs modestly more or is materially better;
- no default 1000–1200 W requirement.

Prioritize electrical design/protections, long warranty, acoustics and exact current revision/cabling over wattage.

## UPS / mains protection

No UPS initially. Use a reputable point-of-use surge protector / surge-protected power strip with a protection-status indicator.

## Hard purchase gates

### Motherboard
- **ASUS TUF GAMING B850-PLUS WIFI**;
- exact part `90MB1J30-M0EAY0`;
- current/new retail board;
- update to a current stable production BIOS during commissioning.

### RAM
- exact **Crucial `CT2K64G56C46U5`** matched 2×64 GB kit;
- non-ECC UDIMM;
- DDR5-5600 CL46 / 1.1 V native JEDEC;
- no substitution with RDIMM or a different-capacity topology.

### Cooler
- **Thermalright Phantom Spirit 120 standard**;
- AM5 hardware included;
- no silent SE/EVO substitution.

### Case
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- two included 140 mm PWM fans present.

### Storage
- active-work NVMe on CPU-direct M.2;
- system drive target ~1 TB, preferably NVMe on the second CPU M.2;
- no Gen5 requirement;
- no RAID requirement.

### PSU
- premium 750/850 W class;
- ATX 3.1/current PCIe GPU-power standard;
- strong protections, mature platform and long warranty.

### UPS
- **do not purchase one initially**.

### Windows
- Windows 11 Pro Retail/FPP;
- current target `HAV-00163` English USB from PROstore.

## Next decision sequence

1. Select exact **system + active-work SSDs** using current Romanian prices.
2. Select exact premium **750 W / 850 W PSU**.
3. Select exact plug-in surge protector.
4. Refresh all prices/provider consolidation and produce the order total.

Detailed decisions: `docs/decisions.md`.
