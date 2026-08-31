# Decision Log

This file records closed decisions plus any decision explicitly reopened because a requirement changed.

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | Fits the very heavy Java/Android workload while retaining excellent occasional gaming performance without workstation-platform TCO/specialization. |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Selected** | Meets the actual requirements at sub-1k-leu pricing without unused B850/Creator premiums. |
| Final memory capacity | **48 GB from day one** | **Selected / final** | Current 128 GB pricing is economically disproportionate; 48 GB preserves full two-DIMM memory topology and is sufficient as the best current utility-per-leu point. |
| Final memory topology | **2×24 GB DDR5 UDIMM, one DIMM per channel (1DPC), A2/B2** | **Selected / final** | Preserves the electrically favorable two-DIMM topology and Ryzen 9000 DDR5-5600 support path. |
| Exact memory kit | **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24), DDR5-5600 CL46, 1.1 V** | **Selected** | Conservative JEDEC-oriented 5600-class kit, low voltage, matched two-DIMM topology and current Romanian pricing around ~2.9k lei. |
| Memory upgrade policy | **Do not add another pair later** | **Selected** | If 48 GB proves insufficient, replace the kit with a larger 2-DIMM kit rather than moving to 4 DIMMs; AMD officially rates four-DIMM Ryzen 9 9950X3D configurations at DDR5-3600. |
| ECC policy | **Non-ECC** | **Selected** | ECC availability is not worth distorting capacity/topology. |
| Memory operating policy | **Auto/JEDEC first; target DDR5-5600 at conservative voltage; no EXPO/XMP required** | **Selected** | Stability outranks benchmark timings. |
| Cooling architecture | **High-quality air cooling, stock/conservative CPU operation** | **Selected** | Avoid pump/liquid complexity unless measurements justify it. |
| Exact CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** | Strong sustained cooling at good value. |
| Chassis | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** | Appropriate ATX envelope without oversizing. |
| Initial case airflow | **Two included 140 mm PWM fans: one front intake + one rear exhaust** | **Selected** | Add another intake only if measurements justify it. |
| Storage architecture | **One primary 2 TB NVMe from day one; no separate system/work SSD, no SSD cache layer, no automatic tiering** | **Selected / final** | Current usage is ~600 GB and foreseeable active demand remains below 2 TB. |
| Exact primary SSD | **Crucial T710 2 TB `CT2000T710SSD8` in CPU-direct `M.2_1`** | **Selected** | PCIe 5.0 x4, TLC, DRAM and good current value. |
| Bulk/cold storage | **Reuse existing healthy SATA drives where appropriate; add NVMe only when concretely needed** | **Selected expansion policy** | Existing slower storage is adequate for archives/cold data. |
| Storage RAID policy | **No RAID required** | **Selected** | Version control and independent backup are more relevant. |
| Wired networking | **1 GbE sufficient; 2.5 GbE a bonus; do not pay for 5/10 GbE** | **Selected** | LAN throughput is not a requirement. |
| Secondary PCIe expansion | **No x4 secondary slot requirement** | **Selected** | No concrete high-bandwidth add-in requirement exists. |
| Multi-GPU | **Not a requirement; retire RTX 3060 on future replacement** | **Selected** | CPU x8/x8 support is not needed. |
| GPU | **Reuse RTX 3060 12 GB for as long as useful/reliable** | **Selected** | Gaming is secondary. |
| Future GPU policy | **Do not pre-provision for a hypothetical 500–600 W flagship GPU** | **Selected** | Revisit replaceable parts only when a concrete need appears. |
| Exact PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | **Selected** | ATX 3.1, excellent acoustics, long warranty and small premium over 750 W. |
| PSU fallback | **Corsair RM850x 2024 `CP-9020270-EU`** | **Fallback** | Use only if checkout value/warranty becomes materially better. |
| UPS | **No UPS in the initial BOM** | **Selected** | Continuity is unnecessary. |
| Point-of-use surge protection | **No dedicated surge protector required** | **Selected** | Use a properly earthed wall outlet or ordinary reputable 16 A Schuko strip if needed. |
| Motherboard VRM / OC | **Stock/conservative 9950X3D only** | **Selected** | No value in extreme OC capability. |
| Host OS | **Windows 11 Pro x64** | **Selected** | Best fit for the workload. |
| Windows license | **Already available** | **Closed / no procurement action** | Windows remains the selected host OS, but license sourcing and cost are outside the remaining build procurement. |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual boot. |
| Cost philosophy | **Optimize utility per leu; do not spend for prestige, unused capacity or speculative future-proofing** | **Selected** | Premiums must buy durable value. |
| Provider consolidation | **Maximum 3 providers; default target 2 for hardware** | **Selected** | Extra fragmentation needs meaningful value. |

## Explicitly superseded decisions

### Memory
- 128 GB / 2×64 GB as the initial purchase;
- Crucial `CT2K64G56C46U5` as the purchase target;
- 64 GB / 2×32 GB as the preferred value target;
- 96 GB / 2×48 GB;
- 256 GB / 4×64 GB endpoint;
- any planned four-DIMM upgrade path;
- ECC as a purchase requirement.

### Motherboard / cooling / storage / power
- ASUS ProArt X870E-Creator WiFi;
- ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`;
- treating B850 as a requirement;
- Noctua NH-D15 G2;
- Fractal North XL Mesh;
- dedicated extra premium case fan;
- separate system/work SSDs;
- SSD cache/tiering;
- fixed 4 TB initial SSD;
- premium 750 W as selected PSU target;
- 1200 W Seasonic VERTEX targets;
- CyberPower PR1500ELCD;
- dedicated surge protector purchase.

### Operating system procurement
- Windows 11 Pro Retail/FPP `HAV-00163` English USB as a remaining purchase target; the license is already available.

## Open / deferred decisions

- optional future RAM replacement only if measured memory pressure proves 48 GB insufficient;
- optional future storage expansion only if actual capacity needs grow;
- future GPU replacement only when a concrete need/failure appears;
- mains protection only if actual power-quality problems appear.

Detailed component dossiers are under `docs/components/`.
