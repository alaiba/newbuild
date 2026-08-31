# Decision Log

This file records closed decisions plus any decision explicitly reopened because a requirement changed.

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | Fits the very heavy Java/Android workload while retaining excellent occasional gaming performance without workstation-platform TCO/specialization. |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Selected** | Meets the actual requirements at ~0.84k-leu reference pricing: PCIe 5.0 x16 graphics, two CPU-direct M.2 paths, full Gen4 x4 third M.2, 256 GB platform capacity, FlashBack/Q-LED, 4 SATA, 2.5 GbE and sufficient stock-load power delivery. B850 features do not currently justify their premium. |
| Final memory capacity | **128 GB from day one** | **Selected / final** | Buy the intended lifetime capacity at initial assembly. |
| Final memory topology | **2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC), A2/B2** | **Selected / final** | Preserves the electrically favorable 1DPC topology. |
| Exact memory kit | **Crucial `CT2K64G56C46U5` — 128 GB (2×64), DDR5-5600 CL46, 1.1 V** | **Selected** | Native JEDEC-5600, low voltage and low-profile modules fit the stability-first policy; commissioning will validate the exact kit on the selected board. |
| ECC policy | **Non-ECC for the final 2×64 GB configuration** | **Selected** | CPU/board support ECC UDIMM, but practical mainstream 64 GB ECC UDIMM availability is poor; current server 64 GB parts are usually RDIMM and incompatible with AM5. Do not distort capacity/topology to obtain ECC. |
| Memory operating policy | **Auto/JEDEC first; target native DDR5-5600 at 1.1 V; no EXPO/XMP required** | **Selected** | Stability and conservative voltage outrank tighter timings/OC profiles. |
| Cooling architecture | **High-quality air cooling, stock/conservative CPU operation** | **Selected** | Avoid pump/liquid complexity unless a real measured thermal requirement appears. |
| Exact CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** | Strong sustained air-cooling capability at much lower cost/size than NH-D15 G2-class alternatives. |
| Chassis | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** | Normal ATX mid-tower with useful cooler/GPU/storage clearance without North XL overprovisioning. |
| Initial case airflow | **Two included 140 mm PWM fans: one front intake + one rear exhaust** | **Selected** | Add another front intake only if measurements justify it. |
| Storage architecture | **One primary 2 TB NVMe from day one; no separate system/work SSD, no SSD cache layer, no automatic tiering** | **Selected / final** | Current usage is ~600 GB and foreseeable active-storage demand remains below 2 TB; one fast SSD keeps all latency-sensitive data local while avoiding needless storage complexity. |
| Exact primary SSD | **Crucial T710 2 TB `CT2000T710SSD8` in CPU-direct `M.2_1`** | **Selected** | PCIe 5.0 x4, TLC, DRAM, strong sustained behavior and a small enough premium over premium Gen4 to justify using the board's Gen5 path. Use the non-heatsink version under the motherboard heatsink. |
| Bulk/cold storage | **Reuse existing healthy SATA drives where appropriate; add NVMe only when concretely needed** | **Selected expansion policy** | Existing slower storage is adequate for archives, old projects, media, installers, inactive VMs and other cold data. `M.2_2` and `M.2_3` remain free. |
| 4 TB primary SSD | **Not required initially** | **Rejected on value/capacity** | Roughly doubling current selected-drive cost for capacity that is not expected to be used soon is inferior to additive expansion later. |
| Storage RAID policy | **No RAID required** | **Selected** | Version control and real independent backup solve more relevant failure modes. |
| Wired networking | **1 GbE sufficient; 2.5 GbE a bonus; do not pay for 5/10 GbE** | **Selected** | Internet is below 1 Gb/s and LAN throughput is irrelevant. |
| Secondary PCIe expansion | **No x4 secondary slot requirement** | **Selected** | The selected board's second full-length slot is x1. No concrete NIC/HBA/capture/second-GPU requirement justifies paying extra to preserve x4 expansion. |
| Multi-GPU | **Not a requirement; retire RTX 3060 on future replacement** | **Selected** | CPU x8/x8 support is not needed. |
| GPU | **Reuse RTX 3060 12 GB for as long as useful/reliable** | **Selected** | Gaming is secondary and cloud AI reduces the need to pre-buy local accelerator capability. |
| Future GPU policy | **Do not pre-provision for a hypothetical 500–600 W flagship GPU** | **Selected** | Reconsider replaceable PSU/case only if a concrete future GPU requires it. |
| PSU architecture | **Reopened around premium 750 W and 850 W ATX 3.1 units** | **Reopened** | 750 W is a legitimate long-term target; 850 W is a value-dependent upgrade. |
| PSU sizing rule | **Prefer 750 W unless an equally high-quality 850 W model costs only modestly more or is materially better** | **Selected optimization rule** | Quality outranks speculative wattage. |
| UPS | **No UPS in the initial BOM** | **Selected** | Short outages are acceptable operationally; continuity is unnecessary. |
| Point-of-use power protection | **Use a reputable plug-in surge protector / surge-protected power strip** | **Selected policy** | Objective is transient/surge risk reduction without electrical-installation modification. |
| Motherboard VRM / OC | **Stock/conservative 9950X3D only; extreme VRM/OC capability has no value** | **Selected** | Require comfortable stock-load margin and stability, not phase-count marketing. |
| Host OS | **Windows 11 Pro x64** | **Selected** | Best fit for development, virtualization, NVIDIA/gaming and professional host features. |
| Windows license | **Retail/FPP `HAV-00163` English USB** | **Selected purchase target** | Clean DIY licensing path; PROstore remains current reference supplier. |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual-boot friction. |
| Cost philosophy | **Optimize utility per leu; do not spend for prestige, unused capacity or speculative future-proofing** | **Selected** | Premiums must buy a material durable benefit. |
| Provider consolidation | **Maximum 3 providers; default target 2 for hardware** | **Selected** | Extra supplier fragmentation needs meaningful value. |

## Explicitly superseded decisions

### Motherboard / memory
- ASUS ProArt X870E-Creator WiFi as the incumbent/provisional board;
- ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0` as the selected mainstream board;
- treating B850 itself as a platform requirement;
- ASRock Creator-class features as selection drivers;
- 256 GB / 4×64 GB endpoint;
- 64 GB / 2×32 GB Phase-1 RAM;
- Crucial `CT2K32G56C46U5` as a purchase target;
- ECC as a requirement for the 128 GB endpoint;
- motherboard premiums for 5/10 GbE, x8/x8, a secondary x4 slot, many Gen5 M.2 slots or extreme VRM capability.

### Cooling / chassis
- Noctua NH-D15 G2;
- Fractal North XL Mesh `FD-C-NOR1X-01`;
- dedicated Noctua NF-A14x25 G2 rear fan.

### Storage / power
- Samsung 990 PRO 2 TB as selected system drive;
- separate ~1 TB system SSD + 1–2 TB active-work SSD architecture;
- a dedicated small SSD cache in front of another SSD;
- automatic SSD tiering / Storage Spaces as an initial architecture;
- fixed 4 TB high-performance work SSD;
- reserving the Gen5 M.2 slot instead of using it for the initial primary SSD;
- 1200 W Seasonic VERTEX GX/PX targets;
- CyberPower PR1500ELCD.

## Open / deferred decisions

- exact premium 750 W or 850 W PSU;
- exact plug-in surge protector;
- optional future storage expansion only if actual capacity needs grow;
- future GPU replacement only when a concrete need/failure appears.

Detailed component dossiers are under `docs/components/`.
