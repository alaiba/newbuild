# Final Build

This document is the current bill-of-materials view. Closed decisions are fixed inputs unless explicitly reopened; deferred items remain subject to their stated future purchase gates.

## Selected initial build

| Component | Model / configuration | Status | Current price reference |
|---|---|---|---:|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | ~3.35–3.52k lei |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | ~2.68–2.90k lei market range |
| Phase-1 memory | **Crucial `CT2K32G56C46U5`, 64 GB (2×32 GB), DDR5-5600 CL46, 1.1 V** | **Selected target** | ~4.7–4.8k lei current low market |
| Long-term memory | **256 GB target, expected 4×64 GB** | **Target selected / purchase deferred** | Deferred |
| CPU cooler | **Noctua NH-D15 G2 standard base, 7 mm AM5 offset** | **Selected** | ~0.69–0.73k lei |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | ~1.90–1.95k lei |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / purchase deferred** | Deferred |
| PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | ~1.29k lei explicit Altex ATX 3.1 listing |
| Case | **Fractal Design North XL Mesh** | **Selected** | ~0.93–1.06k lei current market class |
| Rear case fan | **Noctua NF-A14x25 G2 PWM** | **Selected** | ~0.19–0.21k lei |
| Case-fan layout | **3× included 140 mm front intake + 1× Noctua rear exhaust** | **Selected** | Front fans included |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | 0 lei initial-build spend |
| UPS | **CyberPower CP1600EPFCLCD** | **Selected** | ~1.53–1.59k lei |
| OS | — | Open | — |

## Final initial-BOM cost review — 2026-08-31

Using current Romanian price controls rather than assuming every component can be bought at the absolute cheapest listing:

- non-RAM selected hardware: approximately **12.6–13.3k lei**;
- with the previous 32 GB GOODRAM minimum: approximately **14.8–15.5k lei**;
- with the selected Crucial 64 GB kit: approximately **17.3–18.1k lei**;
- with a more expensive Kingston 64 GB fallback: approximately **17.9–18.8k lei**.

These totals exclude the existing RTX 3060 because it is reused and exclude the deferred future work SSD and future GPU.

The 64 GB configuration therefore remains roughly **11k+ lei below the ~30k planning level**. No permanent component needs to be downgraded to fund the additional memory.

## Phase-1 memory decision

The final 32-vs-64 review is now closed in favor of **64 GB (2×32 GB)**.

Preferred exact kit:

- **Crucial `CT2K32G56C46U5`**;
- 2×32 GB;
- DDR5-5600 CL46;
- 1.1 V;
- low-profile bare UDIMMs;
- non-ECC;
- lifetime-class manufacturer warranty.

Why it wins:

- doubles capacity over the minimum 32 GB configuration;
- restores dual-channel bandwidth;
- materially improves headroom for IntelliJ, Android Studio, emulators, Maven/Gradle, Docker/WSL2, local services and VMs;
- uses a conservative 1.1 V electrical profile and does not depend on EXPO/XMP for normal operation;
- keeps the complete initial build well below the planning level.

Fallback if the Crucial purchase path becomes poor:

- **Kingston FURY Beast `KF556C36BBEK2-64`**, 2×32 GB DDR5-5600 CL36 EXPO.

Kingston explicitly lists that kit for the ProArt X870E-Creator WiFi, but its current ~5.5k lei PC Garage price is not worth a ~700–800 lei premium over a normal ~4.7–4.8k Crucial offer unless Crucial stock/warranty is materially worse.

The old 32 GB GOODRAM `GR5600D564L46/32G` remains an emergency/minimum-cost fallback only.

## Memory bring-up policy

1. install the two DIMMs in the motherboard-recommended A2/B2 slots;
2. update BIOS before serious validation;
3. boot at **Auto/JEDEC** first;
4. do not enable EXPO/XMP during baseline validation;
5. prioritize stability over advertised speed;
6. run extended memory testing;
7. record exact DIMM SKU, BIOS version, trained rate and timings.

The eventual 256 GB configuration remains a separate matched-set purchase. Prefer ECC UDIMM only if exact 64 GB modules, four-DIMM operation and OS-visible ECC reporting are credible; otherwise use validated non-ECC. RDIMM is incompatible with AM5.

## Cooling strategy

Selected configuration:

- **Noctua NH-D15 G2 standard medium-convexity base**;
- included **7 mm AM5 offset** mount;
- stock/conservative Ryzen 9 9950X3D settings;
- no PBO/uncapped-power policy.

The Crucial 64 GB kit uses low-profile bare modules around the low-30-mm height class. The NH-D15 G2 has approximately 32 mm normal RAM clearance, so expect **zero or only minimal front-fan lift**. Even a small lift leaves substantial margin under the North XL's 185 mm CPU-cooler limit.

## Storage strategy

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` in **`M.2_3`** as permanent system/tools drive;
- reserve **`M.2_1`** for future 4 TB+ work/VM/container/data drive;
- avoid `M.2_2` unless its graphics-lane trade-off is intentionally accepted;
- no RAID; external/network backup remains required.

## PSU strategy

Selected exact PSU:

**Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision.**

Current explicit Romanian purchase reference is Altex around **1,289.99 lei** for the ATX 3.1 listing.

Receipt acceptance:

1. box/listing says **ATX 3.1**;
2. product is PCIe 5.1 compatible;
3. supplied GPU cable is **12V-2x6**;
4. reject ATX 3.0 / 12VHPWR old inventory;
5. retain model/serial/warranty evidence.

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

## Procurement policy

- **PC Garage and Altex are co-preferred retailers**;
- **eMAG is also acceptable**;
- exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order;
- small price differences do not matter;
- material price differences may justify another reputable Romanian/EU seller, especially for temporary memory.

## Remaining purchase-time gates

### Phase-1 memory

- target **Crucial `CT2K32G56C46U5`** around the current ~4.7–4.8k lei class;
- if its price rises materially or warranty/seller quality is poor, compare Kingston `KF556C36BBEK2-64`;
- boot at Auto/JEDEC and validate extensively.

### PSU

- exact model is selected; verify the received unit is current ATX 3.1 / 12V-2x6 stock.

### Future work SSD

- deferred until capacity is actually needed.

### OS

- still open.

## Bring-up and validation

- BIOS update before serious memory testing;
- Auto/JEDEC 64 GB memory baseline and extended memory stability test;
- update Samsung 990 PRO firmware and record SMART baseline;
- sustained CPU thermal validation with NH-D15 G2;
- combined CPU/GPU thermal test with case closed;
- tune fan curves for sustained workloads rather than Ryzen transients;
- inspect PSU/GPU connectors for full insertion and strain-free routing;
- validate sleep/resume, WSL2, virtualization and 10 GbE drivers;
- connect CP1600EPFCLCD by USB, configure graceful shutdown and perform a controlled power-loss test.
