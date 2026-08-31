# Final Build

This document is the current bill-of-materials view. Closed decisions are fixed inputs unless explicitly reopened; provisional/optional items remain subject to the stated purchase gate.

## Selected and current-target components

| Component | Model / configuration | Status | Notes |
|---|---|---|---|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | AM5; stock/conservative operating policy |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | Selected for strongest explicit 4×64 GB / 256 GB firmware evidence and ECC-specific firmware trail |
| Phase-1 memory baseline | **GOODRAM 32 GB DDR5-5600 CL46 `GR5600D564L46/32G`, 1×32 GB** | **Baseline selected / final capacity choice deferred** | Minimum-sunk-cost commissioning configuration; ~2,199.99 lei at PC Garage |
| Phase-1 memory optional tier | **64 GB (2×32 GB)** | **Optional / under review** | Current candidates: Crucial `CT2K32G56C46U5`; Kingston `KF556C36BBEK2-64`; Kingston `KF560C36BBEK2-64`. Final 32-vs-64 choice at end of BOM review. |
| Long-term memory | **256 GB target, expected 4×64 GB** | **Target selected / purchase deferred** | Prefer ECC UDIMM only if exact modules, stability and OS-visible ECC reporting are credible |
| CPU cooler | **Noctua NH-D15 G2 standard base, 7 mm AM5 offset** | **Selected** | High-end air; no PBO/uncapped power policy |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | Bare drive in ProArt `M.2_3`; permanent system/tools role |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / purchase deferred** | Reserve CPU-connected `M.2_1`; reassess Gen4/Gen5 and 4/8 TB later |
| PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | 1200 W, fully modular, 12-year warranty. Reject ambiguous ATX 3.0 / 12VHPWR old stock. |
| Case | **Fractal Design North XL Mesh** | **Selected** | 185 mm cooler clearance, strong filtration/airflow, future large-GPU headroom |
| Rear case fan | **Noctua NF-A14x25 G2 PWM** | **Selected** | One 140 mm rear exhaust |
| Case-fan layout | **3× included 140 mm front intake + 1× Noctua rear exhaust** | **Selected** | No top/side fans initially |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | Reuse initially |
| UPS | **CyberPower CP1600EPFCLCD** | **Selected** | 1600 VA / 1000 W pure-sine line-interactive; reassess with future high-power GPU |
| OS | — | Open | |

## Memory decision for final purchase review

The Phase-1 capacity decision is deliberately still open even though the **32 GB GOODRAM configuration is the baseline**.

### 32 GB baseline

- GOODRAM `GR5600D564L46/32G`
- 1×32 GB
- DDR5-5600 CL46, 1.1 V
- current PC Garage price: approximately **2,199.99 lei**
- single-channel is accepted because the memory is temporary
- 31.25 mm module height fits under NH-D15 G2 with no front-fan lift

### Optional 64 GB tier

Preferred topology: **2×32 GB**.

Current serious candidates:

1. **Crucial `CT2K32G56C46U5`** — 64 GB (2×32), DDR5-5600 CL46, 1.1 V; current broader Romanian pricing roughly **4.7–4.8k lei**. Current value/control leader.
2. **Kingston FURY Beast `KF556C36BBEK2-64`** — 64 GB (2×32), DDR5-5600 CL36 EXPO, 1.25 V; explicitly listed by Kingston for the ProArt; current PC Garage indexing roughly **5.56k lei**.
3. **Kingston FURY Beast `KF560C36BBEK2-64`** — 64 GB (2×32), DDR5-6000 CL36 EXPO; explicitly listed by Kingston for the ProArt; recent PC Garage indexing has shown around **5.0k lei**, but pricing is volatile.

A **1×64 GB** module such as Kingston `KVR56U46BD8-64` is technically compatible and explicitly listed for the ProArt, but current pricing around **5.1k lei+** makes it poor value because it remains single-channel while costing as much as or more than good 2×32 kits.

### Final decision rule

Refresh prices after the rest of the initial BOM is closed.

Working guide:

- **≤ ~4.5k lei:** 64 GB 2×32 is strongly attractive;
- **~4.5–4.8k lei:** serious consideration;
- **~5.0k lei or more:** 32 GB baseline normally wins unless the final build has substantial unused budget or workload needs have changed.

The 64 GB premium buys **both another 32 GB of capacity and dual-channel bandwidth**, so the comparison is not just capacity-per-leu. However, either Phase-1 configuration will eventually be replaced by the validated 256 GB endpoint, so sunk cost still matters.

Detailed memory evidence: `docs/components/memory.md`.

## Memory bring-up policy

Whether 32 GB or 64 GB is chosen:

1. install in the motherboard-recommended slot(s);
2. update BIOS before serious validation;
3. boot at **Auto/JEDEC** first;
4. treat EXPO/XMP as optional;
5. do not sacrifice stability to preserve advertised memory speed;
6. run extended memory testing;
7. record exact DIMM SKU and trained speed/timings.

For the final 256 GB configuration, prefer 4×64 GB ECC UDIMM only if exact modules, four-DIMM operation and OS-visible ECC reporting are all credible; otherwise use a validated non-ECC matched set. RDIMM is incompatible with AM5.

## Cooling strategy

Selected configuration:

- **Noctua NH-D15 G2 standard medium-convexity base**;
- included **7 mm AM5 offset** mount;
- stock/conservative Ryzen 9 9950X3D settings;
- no PBO/uncapped-power policy.

Clearance:

- cooler stock height: 168 mm;
- North XL limit: 185 mm;
- GOODRAM 32 GB baseline: ~31.25 mm, no front-fan lift required;
- Kingston FURY 64 GB candidates: ~34.9 mm, requiring only ~3 mm lift and yielding ~171 mm total cooler height.

All current serious Phase-1 memory choices fit comfortably.

## Storage strategy

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` in **`M.2_3`** as permanent system/tools drive;
- reserve **`M.2_1`** for future 4 TB+ work/VM/container/data drive;
- avoid `M.2_2` unless its graphics-lane trade-off is intentionally accepted;
- no RAID; external/network backup still required.

Procurement preference for the selected 990 PRO remains **PC Garage first, eMAG second when the difference is small**.

## PSU strategy

Selected exact PSU:

**Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision.**

Permanent requirements satisfied:

- 1200 W;
- ATX 3.1 / PCIe 5.1;
- 600 W-capable 12V-2x6 GPU cable;
- full modularity;
- complete protection set;
- long warranty;
- compact 160 mm body that easily fits North XL.

Current purchase position on 2026-08-31:

- PC Garage/eMAG remain preferred when they explicitly identify the current revision;
- current searches do not expose a sufficiently unambiguous preferred-retailer listing;
- **Altex currently has an explicit VERTEX GX-1200 ATX 3.1 listing around 1,289.99 lei and shown in stock**;
- Media Galaxy's explicit VERTEX PX-1200 ATX 3.1 listing is around 1,449.99 lei but currently shown out of stock.

Therefore do not delay or accept old stock merely to stay with a preferred retailer. If PC Garage/eMAG cannot explicitly confirm ATX 3.1 + 12V-2x6, use a reputable explicit-current listing such as Altex.

Receipt acceptance:

1. box/listing says **ATX 3.1**;
2. product is PCIe 5.1 compatible;
3. supplied GPU cable is **12V-2x6**;
4. reject ATX 3.0 / 12VHPWR old inventory;
5. retain exact model/serial/warranty evidence.

Detailed PSU evidence: `docs/components/psu.md`.

## Chassis and airflow

Selected:

- **Fractal Design North XL Mesh**;
- 3× included 140 mm front intake;
- 1× **Noctua NF-A14x25 G2 PWM** rear exhaust;
- top empty initially;
- side empty initially.

Add more fans only if measured thermals justify them.

## UPS

Selected Phase-1 UPS: **CyberPower CP1600EPFCLCD**.

- line-interactive;
- pure sine wave;
- Active-PFC compatible;
- 1600 VA / 1000 W;
- AVR;
- USB HID / PowerPanel;
- user-replaceable `RBP0142` battery;
- reassess when a materially higher-power GPU is installed or measured load approaches ~700–800 W.

## Remaining purchase-time gates

### Memory

- final **32 GB vs 64 GB** decision after the full BOM total is known;
- refresh PC Garage first, eMAG second, then broader Romanian market as a price control;
- favor 2×32 over 1×64 if choosing 64 GB;
- use conservative Auto/JEDEC bring-up regardless of advertised EXPO/XMP speed.

### PSU

The exact model is selected. Purchase-time work is limited to revision acceptance:

- prefer PC Garage first and eMAG second only if the listing/unit is explicitly current;
- otherwise use an explicit ATX 3.1 Romanian listing;
- verify the received unit includes the 12V-2x6 cable and is not old ATX 3.0 stock.

### Future work SSD

- deferred until capacity is actually needed.

### OS

- still open.

## Bring-up and validation

- BIOS update before serious memory testing;
- Auto/JEDEC memory baseline and extended memory stability test;
- update Samsung 990 PRO firmware and record SMART baseline;
- sustained CPU thermal validation with NH-D15 G2;
- combined CPU/GPU thermal test with case closed;
- tune fan curves for sustained workloads rather than Ryzen transients;
- inspect PSU/GPU connectors for full insertion and strain-free routing;
- validate sleep/resume, WSL2, virtualization and 10 GbE drivers;
- connect CP1600EPFCLCD by USB, configure graceful shutdown and perform a controlled power-loss test.
