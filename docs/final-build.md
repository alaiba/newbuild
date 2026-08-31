# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Selected** |
| RAM | **Crucial `CT2K64G56C46U5` — 128 GB (2×64 GB) DDR5-5600 CL46, 1.1 V, non-ECC** | **Selected** |
| Memory topology | **1DPC / A2+B2; Auto/JEDEC first** | **Selected** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** |
| Case airflow | **2× included 140 mm PWM: front intake + rear exhaust** | **Selected initial layout** |
| Primary storage | **Crucial T710 2 TB `CT2000T710SSD8`**, PCIe 5.0 x4 TLC NVMe in CPU-direct `M.2_1` | **Selected** |
| Bulk/cold storage | Reuse healthy existing SATA drives; `M.2_2` + `M.2_3` remain free for future expansion | **Selected policy** |
| Storage RAID/cache/tiering | **None** | **Selected** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`**, ATX 3.1 | **Selected** |
| PSU fallback | Corsair RM850x 2024 850W `CP-9020270-EU` | **Fallback only** |
| UPS | **None initially** | **Selected** |
| Dedicated surge protection | **None required** | **Selected** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse for as long as useful/reliable** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Motherboard — final

Selected board: **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

It wins because it satisfies the actual workstation requirements at roughly the ~0.84k-leu reference price without paying for unused B850/Creator capabilities:

- ATX, fitting the Pure Base 501;
- Ryzen 9000 / 9950X3D support and an actively maintained BIOS branch;
- 256 GB maximum platform memory support, with ASUS memory-support categories covering 2×64 GB and DDR5-5600 configurations;
- primary **PCIe 5.0 x16** graphics path;
- **M.2_1 CPU PCIe 5.0 x4** and **M.2_2 CPU PCIe 4.0 x4**;
- **M.2_3 chipset PCIe 4.0 x4** for later storage;
- four SATA ports;
- BIOS FlashBack and Q-LED CPU/DRAM/VGA/BOOT diagnostics;
- 8+2+1 80 A power stages with enlarged VRM heatsinks, comfortably aligned with stock/conservative 9950X3D operation;
- 2.5 GbE and Wi-Fi 6E, already beyond the actual network requirement;
- front-panel USB-C header at 20 Gb/s.

### Accepted expansion trade-off

The board's second physical x16 slot is chipset-connected and operates only at **PCIe 4.0 x1**. This means the build deliberately gives up a meaningful secondary x4 add-in-card path.

That is accepted because there is no planned need for a high-speed discrete NIC, HBA/RAID controller, capture card or second GPU. If a concrete x4 add-in requirement appears later, motherboard replacement can be reconsidered then rather than paid for speculatively today.

The previous TUF B850-PLUS and Creator-class analyses are superseded as purchase decisions. Their stronger VRM, newer wireless/network options, richer rear I/O or secondary x4 expansion are real features, but none currently maps strongly enough to the workload to justify the premium.

## Memory — final

Selected kit:

> **Crucial `CT2K64G56C46U5` — 128 GB (2×64 GB), DDR5-5600 CL46, 1.1 V, non-ECC UDIMM.**

Reasons:

- exact lifetime capacity in one matched two-DIMM kit;
- electrically favorable **1DPC** topology;
- native **JEDEC DDR5-5600 at 1.1 V**, so no EXPO/XMP profile is needed to reach the intended operating rate;
- conservative timings/voltage match the stability-first objective;
- low-profile modules fit cleanly with the Phantom Spirit 120;
- AMD officially supports DDR5-5600 for two-DIMM Ryzen 9 9950X3D configurations, and the selected board explicitly supports 2×64 GB/5600-class memory configurations.

The exact Crucial part remains subject to normal commissioning validation on this exact board; do not convert general platform support into a claim that every DIMM revision is pre-qualified.

### ECC verdict

The 9950X3D and selected ASUS board support ECC UDIMM. However, the fixed 128 GB / 2×64 GB target makes ECC impractical today: mainstream 64 GB ECC **UDIMM** availability is poor, while readily available 64 GB server modules are generally **RDIMM**, which AM5 cannot use.

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

## Storage architecture — final

Use one primary NVMe drive from day one:

> **Crucial T710 2 TB `CT2000T710SSD8`**, installed in **`M.2_1` CPU PCIe 5.0 x4** under the motherboard M.2 heatsink.

The workstation currently uses about **600 GB**. Even with more ambitious projects, 2 TB is expected to provide ample active-storage headroom for the foreseeable future. The primary SSD can therefore hold Windows, applications, repositories, build caches, WSL2, containers, Android emulator data, active VMs/databases, games and other current data without requiring a second performance SSD.

The remaining topology is deliberately left open:

- **M.2_1 CPU Gen5 x4:** Crucial T710 2 TB — primary storage;
- **M.2_2 CPU Gen4 x4:** empty — future expansion;
- **M.2_3 chipset Gen4 x4:** empty — future expansion;
- **4× SATA:** reuse healthy existing slower drives for archives/cold data.

No separate system/work SSD split is required. No SSD cache layer or Fusion/Storage-Spaces-style automatic tiering is used. No RAID is required.

### Why 2 TB rather than 4 TB

A 4 TB Gen5 drive is technically attractive but currently adds roughly another ~1.3k lei over the selected 2 TB class while buying capacity that is not expected to be used soon. Storage expansion is easy and additive, so paying for that unused capacity now conflicts with the build's utility-per-leu rule.

### Why Gen5 rather than premium Gen4

Gen4 remains fast enough for the workload, but the current price premium for the selected T710 over credible premium Gen4 alternatives is small enough to justify using the board's already-available CPU-direct Gen5 path. This is not based on expecting 2x application performance from 2x sequential bandwidth; it is a value decision at current pricing.

### Thermal/commissioning policy

Use the **non-heatsink** T710 variant under the ASUS motherboard M.2 heatsink. During bring-up, update/record firmware, inspect SMART data and validate sustained-write temperatures under representative workloads.

## GPU policy

Reuse the RTX 3060 for as long as useful/reliable. A future replacement retires it rather than creating a dual-GPU design. Do not distort motherboard or chassis choices around an unknown future flagship GPU.

## PSU — final

Selected:

> **be quiet! Pure Power 13 M 850W `BP027EU`**

The 750 W class remains technically sufficient for the current 9950X3D + RTX 3060 system. The 850 W unit wins because the observed premium over the corresponding 750 W model is only roughly 40–100 lei while retaining premium ATX 3.1 platform quality, native current-generation GPU power, excellent measured acoustics/electrical behavior and a 10-year warranty.

This does **not** restore the former 1000–1200 W future-GPU strategy. If a concrete future accelerator genuinely requires more than this PSU can support, replace the PSU then.

Preferred checkout fallback: **Corsair RM850x 2024 `CP-9020270-EU`** only if delivered price is within roughly 30–40 lei or retailer/warranty conditions are materially better.

## UPS / mains protection — final

No UPS and no dedicated surge protector are purchased initially.

Use a properly earthed wall outlet. If multiple outlets are required, a reputable ordinary **16 A Schuko power strip** is sufficient; it is treated as a utility item rather than a protection component in the BOM.

The selected PSU provides its own normal input/protection circuitry. Revisit external mains protection only if actual power-quality symptoms or failures appear in the building.

## Hard purchase gates

### Motherboard
- **ASUS TUF GAMING B650E-E WIFI**;
- exact part `90MB1LT0-M0EAY0`;
- current/new retail board;
- update to a current stable production BIOS during commissioning;
- no substitution to B650-E/B650E-PLUS or another similarly named TUF SKU without review.

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
- exact **Crucial T710 2 TB `CT2000T710SSD8`**;
- bare/non-heatsink variant;
- install in **CPU-direct `M.2_1` PCIe 5.0 x4** under motherboard heatsink;
- no second NVMe initially;
- no SSD cache/tiering;
- no RAID requirement.

### PSU
- exact **be quiet! Pure Power 13 M 850W `BP027EU`**;
- ATX 3.1/current native GPU-power cabling;
- new retail unit with normal 10-year manufacturer warranty path;
- use only the modular cables supplied with the exact PSU;
- Corsair RM850x 2024 `CP-9020270-EU` is fallback only after price/warranty review.

### UPS / surge protection
- **do not purchase a UPS initially**;
- **do not purchase a dedicated surge protector initially**.

### Windows
- Windows 11 Pro Retail/FPP;
- current target `HAV-00163` English USB from PROstore.

## Next decision sequence

1. Refresh all prices/provider consolidation and produce the order total.

Detailed decisions: `docs/decisions.md`.
