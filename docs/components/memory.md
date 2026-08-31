# Memory Deep Dive

Status: **Phase-1 capacity selected at 64 GB / preferred exact kit selected / 256 GB endpoint deferred**

## Decision

Start the workstation with **64 GB (2×32 GB)** rather than the 32 GB commissioning minimum.

Preferred exact Phase-1 purchase target:

- **Crucial `CT2K32G56C46U5`**
- **64 GB (2×32 GB)**
- DDR5-5600
- CL46
- 1.1 V
- unbuffered desktop UDIMM
- non-ECC
- no heatsink / no RGB
- lifetime-class manufacturer warranty

The previous 32 GB GOODRAM `GR5600D564L46/32G` remains the **minimum-cost fallback**, not the preferred purchase.

## Why 64 GB now wins

The 32 GB option was intentionally retained until the end of the initial BOM review so that temporary RAM would not force cuts to permanent components.

That review is now complete enough to make the decision.

Current initial-build cost envelope on 2026-08-31 is approximately:

- **~14.8–15.5k lei with the 32 GB baseline**;
- **~17.3–18.1k lei with the Crucial 64 GB kit**;
- **~17.9–18.8k lei with the more expensive Kingston 64 GB alternatives**.

The build therefore remains roughly **11k+ lei below the ~30k planning level even with 64 GB**. The extra ~2.5–3k lei no longer threatens the CPU, motherboard, cooler, SSD, PSU, chassis, fan or UPS selections.

For the actual workload, 64 GB provides two benefits immediately:

1. double the capacity available to IntelliJ, Android Studio, emulators, Maven/Gradle, Docker/WSL2, local services and VMs;
2. **dual-channel memory bandwidth**, avoiding the deliberate 1×32 GB single-channel compromise of the minimum configuration.

The 64 GB kit is still temporary relative to the eventual 256 GB endpoint, but it is likely to remain materially more productive during the period before that upgrade.

## Why Crucial `CT2K32G56C46U5`

The Crucial kit is preferred because it matches the stability-first Phase-1 policy:

- 2×32 GB topology;
- DDR5-5600, within the normal Ryzen 9 9950X3D memory class;
- conservative **1.1 V** operating voltage;
- no dependence on EXPO/XMP for basic operation;
- CL46 timings are unimportant compared with capacity and stability for this temporary configuration;
- low-profile bare modules avoid unnecessary CPU-cooler interference;
- Crucial provides a compatibility-upgrade page for the ASUS ProArt X870E-Creator WiFi platform;
- current Romanian market pricing is roughly **4.7–4.8k lei** at the low end.

The exact kit was not independently confirmed as a specific ASUS QVL line item during this pass. That is not considered a blocker because this is a conservative 1.1 V JEDEC-class 2-DIMM configuration, and the motherboard QVL is not an exhaustive support list.

References:

- https://www.crucial.com/compatible-upgrade-for/asus/proart-x870e-creator-wifi
- https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/

## Kingston fallback

If the Crucial kit is unavailable, has an abnormal warranty path, or rises materially in price, use:

- **Kingston FURY Beast `KF556C36BBEK2-64`** — 64 GB (2×32), DDR5-5600 CL36 EXPO.

Kingston explicitly lists this exact kit for the **ASUS ProArt X870E-Creator WiFi**, making it the compatibility-confidence fallback.

Current PC Garage pricing is roughly **5.5k lei**, so paying its current ~700–800 lei premium over a ~4.7–4.8k Crucial kit is not justified unless the Crucial purchase path is materially worse.

The 6000 MT/s Kingston `KF560C36BBEK2-64` remains technically acceptable but is currently much more expensive and should not be bought merely for the higher headline frequency.

Reference:

- https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard

## 32 GB fallback

Keep the previous minimum-cost fallback documented:

- **GOODRAM `GR5600D564L46/32G`**
- 1×32 GB
- DDR5-5600 CL46
- 1.1 V
- approximately 2.2k lei at PC Garage during the current pass.

Use it only if 64 GB pricing jumps materially before ordering or an unexpected budget issue appears elsewhere.

Do not buy a second unmatched GOODRAM module later merely to recover dual-channel operation.

## Cooler clearance

The Crucial modules are low-profile bare UDIMMs. Published dimensions for this kit are around **31–33.5 mm total module height**, depending on measurement convention.

The NH-D15 G2 provides approximately **32 mm** standard RAM clearance with the front fan at stock height.

Therefore:

- the Crucial kit should require **zero or at most a very small front-fan lift**;
- even a ~2 mm lift would put practical cooler height around **170 mm**;
- the Fractal North XL Mesh allows **185 mm** CPU-cooler height;
- there is ample case-side clearance.

The Kingston FURY fallback is ~34.9 mm high and would require only ~3 mm fan lift, yielding ~171 mm total cooler height, also comfortably within the case envelope.

## Bring-up policy

For the selected 64 GB configuration:

1. install both DIMMs in the motherboard-recommended two-DIMM slots, normally A2/B2; confirm against the current manual;
2. update the ProArt BIOS before serious validation;
3. boot at **Auto/JEDEC** first;
4. do not enable EXPO/XMP during baseline validation;
5. accept the trained default rate if firmware chooses a conservative value;
6. run extended memory stability testing before commissioning;
7. record exact SKU, trained data rate, timings and BIOS version.

There is no requirement to tune temporary Phase-1 memory for benchmark latency.

## Eventual 256 GB endpoint

The long-term endpoint remains **256 GB**, expected 4×64 GB or equivalent.

At that upgrade:

1. reassess current ProArt BIOS/AGESA and QVL;
2. identify the best validated 4×64 GB configuration then available;
3. prefer ECC UDIMM only if exact modules, four-DIMM operation, stability and OS-visible ECC reporting are credible;
4. otherwise use a strongly validated non-ECC matched set;
5. start at Auto/JEDEC and accept 5200 MT/s or lower if required for stability;
6. perform extended stability testing;
7. verify actual ECC reporting if ECC is used.

**RDIMM is incompatible with AM5.**

## Selected conclusion

- **Phase-1 capacity:** **64 GB — Selected**.
- **Preferred exact kit:** **Crucial `CT2K32G56C46U5`, 2×32 GB DDR5-5600 CL46 1.1 V**.
- **Kingston compatibility fallback:** `KF556C36BBEK2-64`.
- **32 GB emergency/minimum-cost fallback:** GOODRAM `GR5600D564L46/32G`.
- **Operating policy:** Auto/JEDEC first; stability over headline speed.
- **Long-term endpoint:** 256 GB; exact 4×64 GB and ECC verdict deferred.
