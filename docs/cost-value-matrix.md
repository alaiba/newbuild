# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation. Current prices must be refreshed before purchase.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Avoids Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores/channels/PCIe | Incremental benefit does not justify platform cost/specialization | **Rejected** |
| **ASUS TUF B850-PLUS WIFI `90MB1J30-M0EAY0`** | Stable mainstream AM5 platform, two useful CPU M.2 paths, FlashBack/Q-LED, SATA, adequate VRM | Meets actual requirements at roughly ~1.06k-class pricing without Creator/X870E premiums | **Selected** |
| ProArt / Creator-class board | 10 GbE, richer PCIe/M.2, workstation positioning | Old value case depended on 256 GB, x8/x8, 10 GbE and speculative expansion that are no longer required | **Superseded** |
| **Crucial `CT2K64G56C46U5`, 128 GB 2×64** | Final lifetime capacity in 1DPC, native DDR5-5600 at 1.1 V | Conservative JEDEC operation is more useful than enthusiast timings/profiles | **Selected** |
| 256 GB / 4×64 GB | More capacity | Capacity not expected to be needed; harder 2DPC topology | **Superseded** |
| ECC 2×64 GB | End-to-end correction/detection potential | Platform supports it, but practical 64 GB ECC UDIMM supply is poor; do not distort capacity/topology | **Rejected for current build** |
| 64 GB ECC RDIMM | Server memory density | Incompatible with AM5 | **Rejected / incompatible** |
| High-voltage EXPO 128 GB kit | Tighter timings/headline performance | No material workload benefit versus native 5600/1.1 V JEDEC; often significantly more expensive | **Rejected on value/stability** |
| 5/10 GbE | Higher LAN bandwidth | No meaningful value for this network | **Not required** |
| CPU x8/x8 | Easier dual-GPU layout | No concrete dual-GPU requirement | **Not required** |
| Extreme VRM/OC capability | Very high current headroom | Stock/conservative 9950X3D does not benefit | **Not required** |
| **Thermalright Phantom Spirit 120 standard** | Strong sustained air cooling at low cost/size | Meets actual CPU cooling objective without Noctua/oversized premiums | **Selected** |
| Noctua NH-U12A | Premium fans/mount/support | Real advantages, but not worth current premium for this workload | **Rejected on value** |
| Noctua NH-D15 G2 | Maximum air-cooling headroom | Extra capacity/size/cost no longer justified | **Superseded** |
| **be quiet! Pure Base 501 Airflow `BG074`** | ATX, useful cooler/GPU clearance, included 140 mm fans, HDD path | Provides required physical envelope at much lower size/cost than North XL | **Selected** |
| Fractal North XL Mesh | More E-ATX/GPU/cooler volume | Headroom was driven by hypothetical future hardware | **Superseded** |
| Extra premium case fan | Additional airflow | Measure first; included front/rear 140 mm fans are adequate starting point | **Not initially required** |
| **~1 TB system NVMe** | Adequate OS/tools headroom | Selected board provides clean second CPU M.2, so NVMe now comes without motherboard premium | **Role selected; model open** |
| **1 TB active-work NVMe** | Enough fast working-set capacity | Lowest-cost valid target | **Sufficient baseline** |
| **2 TB active-work NVMe** | More working-set headroom | Prefer when incremental price/value is attractive | **Preferred when well priced** |
| 4 TB active-work NVMe | More capacity | Most excess would hold inactive data | **Not required initially** |
| Gen5 active-work SSD | Higher sequential bandwidth | No demonstrated workload value; selected M.2 can use Gen4 drive perfectly well | **Not required** |
| Later bulk/cold storage | Cheap archive capacity | Add only when needed via M.2/SATA/HDD/external/NAS | **Selected expansion policy** |
| Secondary PCIe x4 slot preserved at all costs | Future add-in-card capability | No planned NIC/HBA/capture/second-GPU use; okay for `M.2_3` to consume it later | **Not required** |
| **Premium 750 W ATX 3.1 PSU** | Plenty for current machine and substantial present-day GPU upgrades | Legitimate baseline; quality matters more than unused wattage | **Preferred baseline class** |
| Premium 850 W ATX 3.1 PSU | More GPU headroom | Choose only for small premium or materially better exact product | **Value-dependent upgrade** |
| 1000–1200 W PSU | Speculative GPU margin | No default justification | **Not required** |
| **No UPS** | Avoids cost/battery maintenance | Short outages are acceptable; continuity not needed | **Selected** |
| Plug-in surge protector | Point-of-use transient protection | Proportional no-installation solution | **Selected policy** |
| Existing RTX 3060 12 GB | Current graphics/CUDA capability with no spend | Keep until failure or concrete upgrade need | **Selected / reuse** |
| Future flagship GPU pre-provisioning | Avoids possible future PSU/case change | Too speculative; efficiency/needs can change and cloud AI is acceptable | **Rejected as design driver** |
| Windows 11 Pro Retail/FPP | Correct DIY licensing path and Pro features | Avoid gray-market/OEM ambiguity | **Selected** |

## Motherboard interpretation

The TUF B850 result demonstrates that the build does not need a workstation-labelled board. At roughly the mainstream ~1.06k lei class it already provides the useful features: strong firmware path, high-capacity memory support, recovery/diagnostics, two CPU-connected M.2 slots, SATA and sufficient power delivery.

Paying another 600–1,800+ lei for 10 GbE, x8/x8 or Creator-class I/O would not improve the actual workload.

## Memory interpretation

The RAM purchase is unusual because the **capacity is valuable but the current market price is poor**.

128 GB remains the final requirement because it directly supports concurrent IDE/JVM/WSL2/container/VM workloads. The correct response to current pricing is to refresh suppliers carefully, not to buy a technically inferior topology or a high-voltage enthusiast kit.

The Crucial kit is selected because native DDR5-5600 / 1.1 V JEDEC operation aligns better with stability than paying more for EXPO timings.

ECC loses on practical module availability at 64 GB density, not because ECC itself lacks value or because the motherboard cannot support it.

## Storage interpretation

With the selected motherboard, system and active-work drives can both be NVMe without consuming the primary GPU link:

- `M.2_1`: active work;
- `M.2_2`: system/tools.

This removes the main reason to consider SATA for C:, although SATA remains valid for later bulk storage.

## PSU interpretation

A premium **750 W ATX 3.1** supply is not an economy compromise. It is the baseline sized to the machine actually expected to operate. An 850 W unit wins only when the exact high-quality model has a small premium or other concrete benefits.

## Premium rule

When two candidates satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage**: better proven stability, materially better acoustics, better recovery/support, longer serviceability, necessary compatibility/topology or endurance the workload will actually use.

Invalid premiums include unused benchmark capability, unused Gen5 lanes, extreme OC features, oversized cooling/case/wattage and speculative future-proofing.
