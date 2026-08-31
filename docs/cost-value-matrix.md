# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation.

Current exact prices must be refreshed before purchase; historical snapshots are not purchase controls.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Keeps mainstream AM5 ecosystem while avoiding Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores, memory channels and PCIe | Incremental benefit does not justify platform cost/specialization | **Rejected** |
| **128 GB = 2×64 GB / 1DPC** | Large concurrency headroom with favorable topology | Avoids temporary RAM and four-DIMM compromises | **Selected / final architecture** |
| 256 GB / 4×64 GB | More capacity | Capacity not expected to be needed and distorts board/memory selection | **Superseded** |
| ECC 2×64 GB | Potential end-to-end error detection/correction | Worth a premium only if exact DIMMs/board/reporting path is credible | **Open / optional** |
| **Broad mainstream AM5 motherboard search** | Same CPU performance without workstation-feature premiums | Creator-class boards must compete on actual stability/serviceability/value | **Reopened** |
| 5/10 GbE | Higher LAN bandwidth | No meaningful value for this network | **Not required** |
| CPU x8/x8 | Easier dual-GPU layout | No concrete dual-GPU requirement | **Not required** |
| Extreme VRM/OC capability | Very high CPU current headroom | Stock/conservative 9950X3D does not benefit | **Not required** |
| **Thermalright Phantom Spirit 120 standard** | Strong sustained air cooling in a compact/low-cost package | Meets the real CPU cooling objective without paying Noctua/oversized-cooler premiums | **Selected** |
| Noctua NH-U12A | Premium fans/mount/support, compact | Durable advantages are real but not worth the large current premium for this workload | **Rejected on value** |
| Noctua NH-D15 G2 | Maximum air-cooling headroom and premium ecosystem | Extra capacity/size/cost no longer justified by stock/conservative operation | **Superseded** |
| AIO liquid cooling | More extreme thermal headroom | Pump/liquid complexity unnecessary unless real validation disproves the air-cooling assumption | **Fallback only** |
| **be quiet! Pure Base 501 Airflow `BG074`** | ATX, 178 mm cooler clearance, 368 mm GPU clearance, 2×140 PWM included, HDD path | Provides the physical/airflow envelope actually needed at much lower size/cost than North XL | **Selected** |
| Fractal North XL Mesh | More GPU/cooler/E-ATX volume | Headroom was driven largely by hypothetical future GPU and NH-D15 G2 | **Superseded** |
| Additional premium rear fan | Better fan quality/airflow | Case already includes suitable front + rear 140 mm PWM fans; measure before adding more | **Not initially required** |
| **~1 TB system storage** | Adequate permanent OS/tools headroom | Optimize reliability/capacity/price; NVMe preferred but SATA acceptable | **Role selected; model open** |
| **1 TB active-work NVMe** | Enough fast capacity for current repos/caches/WSL2/VM data | Lowest-cost valid active-work target | **Sufficient baseline** |
| **2 TB active-work NVMe** | More working-set headroom | Prefer only when incremental price/value is attractive | **Preferred when well priced** |
| 4 TB active-work NVMe | More capacity | Excess likely holds inactive data that does not need performance-tier storage | **Not required initially** |
| Gen5 active-work SSD | Higher sequential bandwidth | Buy only if effectively free or demonstrated workload benefits | **Not required** |
| Later bulk/cold storage | Cheap capacity for archives/inactive data | Add only when needed; NVMe/SATA SSD/HDD/external/NAS all valid | **Selected expansion policy** |
| Reuse healthy old HDD | Near-zero-cost cold capacity | Valid for infrequent data after health checks; never sole copy | **Allowed** |
| **One CPU-direct M.2 x4** | Clean active-work path | Only mandatory M.2 topology requirement | **Required** |
| Second clean M.2 | Convenient NVMe OS drive | Nice to have; SATA system SSD acceptable if board trade-off is meaningful | **Optional** |
| **Premium 750 W ATX 3.1 PSU** | Plenty for current machine and substantial present-day GPU upgrades | Legitimate long-term baseline; quality matters more than unused wattage | **Preferred baseline class** |
| Premium 850 W ATX 3.1 PSU | More GPU headroom | Choose when modest premium or materially better exact platform/acoustics | **Value-dependent upgrade** |
| 1000–1200 W PSU | More speculative GPU headroom | No default justification | **Not required** |
| **No UPS** | Avoids cost/battery maintenance | Short outages are acceptable; continuity not needed | **Selected** |
| Plug-in surge protector | Point-of-use transient protection | Proportional protection measure without electrical-installation changes | **Selected policy** |
| **Windows 11 Pro Retail/FPP** | Correct DIY licensing path and Pro features | Avoid gray-market/OEM ambiguity | **Selected** |
| Existing **RTX 3060 12 GB** | Adequate current graphics/CUDA capability with no spend | Keep until failure or concrete replacement need | **Selected / reuse** |
| Future high-end GPU pre-provisioning | Avoids possible PSU/case replacement later | Too speculative; efficiency/requirements will change and cloud AI is acceptable | **Rejected as current design driver** |

## Cooling / chassis interpretation

The case/cooler optimization demonstrates the governing principle directly:

> buy the smallest/least-expensive durable solution that meets the measured workload, rather than preserving maximum theoretical headroom.

The selected Phantom Spirit 120 + Pure Base 501 combination keeps strong air cooling, ATX serviceability, generous present GPU clearance and HDD expandability while eliminating the cost/volume of NH-D15 G2 + North XL + a separate premium rear fan.

The selected initial two-fan case layout is also deliberately minimal. A third case fan is an inexpensive later addition if measurements justify it, so there is no reason to pre-buy it.

## Motherboard cost/value interpretation

The motherboard must earn its price on:

- stable 9950X3D + 2×64 GB operation;
- mature BIOS/AGESA;
- recovery/diagnostics;
- competent VRM behavior at stock load;
- one CPU-direct M.2 x4 path without compromising the GPU;
- practical SATA/additive storage;
- reliable normal Ethernet;
- serviceability and firmware support;
- **ATX-or-smaller fit** in the selected case.

Do not reward 10 GbE, x8/x8, many Gen5 M.2 slots or extreme VRM specifications unless they come effectively free on the otherwise best board.

## Storage interpretation

- System drive: reliability/headroom/value; SATA remains acceptable.
- Active-work drive: 1 TB sufficient, 2 TB for good-value convenience; mature Gen4 TLC preferred.
- Cold storage: add cheap capacity later rather than oversizing performance storage now.

## PSU interpretation

A premium **750 W ATX 3.1** supply is not an economy compromise. It is the baseline sized to the machine actually expected to operate.

An 850 W unit wins only when the exact high-quality model has a small premium or other concrete benefits. Do not pay substantially for speculative future wattage.

## Premium rule

When two candidates satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage** such as better proven stability, materially better acoustics, better recovery/support, longer serviceability, necessary compatibility/topology or endurance the workload will actually use.

Invalid premiums include unused benchmark capability, unused Gen5 lanes, extreme overclocking features, oversized cooling/case/wattage and speculative future-proofing.
