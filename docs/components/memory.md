# Memory Deep Dive

Status: **32 GB Phase-1 baseline selected / 64 GB Phase-1 option under review / 256 GB endpoint deferred**

## Fixed strategy

The memory strategy has three deliberately distinct levels:

1. **Phase-1 baseline:** 32 GB, sufficient to commission and use the workstation at minimum sunk cost.
2. **Optional Phase-1 upgrade:** 64 GB, to be chosen only if the final purchase-time price delta over 32 GB is attractive enough.
3. **Architectural endpoint:** preserve a credible path to **256 GB**, expected 4×64 GB, with the exact ECC/non-ECC implementation deferred.

Phase-1 RAM remains explicitly **temporary commissioning memory**. Neither the 32 GB nor an optional 64 GB Phase-1 configuration should constrain the eventual 256 GB matched configuration.

The final **32 GB versus 64 GB Phase-1 purchase choice is intentionally deferred until the end of the initial-build purchasing pass**, when the total budget and then-current RAM prices are known.

## 32 GB baseline

Current baseline:

**GOODRAM 32 GB DDR5-5600 CL46 — `GR5600D564L46/32G` — 1×32 GB**

Current purchase position on 2026-08-31:

- PC Garage: approximately **2,199.99 lei**, in stock;
- broader Romanian market: roughly **2.08–2.15k lei**.

Manufacturer characteristics:

- 32 GB, 1×32 GB;
- DDR5 UDIMM, 288-pin desktop memory;
- DDR5-5600 CL46;
- 1.1 V;
- no heatsink / no RGB;
- approximately **31.25 mm** high;
- lifetime manufacturer warranty.

This is the **minimum-sunk-cost reference**. It deliberately gives up dual-channel aggregate bandwidth, but is electrically simple, uses ordinary JEDEC-class settings, satisfies the 32 GB floor and fits under the NH-D15 G2 without raising the front fan.

Do not buy a second unmatched module later merely to convert this temporary configuration to dual-channel. If capacity/bandwidth becomes insufficient, reassess the planned 256 GB upgrade instead.

References:
- https://www.goodram.com/produkty/goodram-ddr5-dimm/
- https://www.price.ro/preturi~goodram-32gb-ddr5-5600mhz-cl46-4737947.html

## Optional 64 GB Phase-1 tier

### Preferred topology: 2×32 GB

If we decide to spend more for 64 GB initially, **2×32 GB is preferred over 1×64 GB**.

Reasons:

- doubles capacity versus the 32 GB baseline;
- restores dual-channel bandwidth;
- two DIMMs are still a straightforward AM5 topology;
- current 2×32 GB pricing is generally as good as or better than current 1×64 GB pricing;
- the optional kit is still temporary, so there is no need to preserve an expansion path through these DIMMs.

A single 64 GB DIMM remains technically valid but is currently poor value: current Kingston ValueRAM `KVR56U46BD8-64` pricing is roughly **5.1k lei or higher**, while credible 2×32 GB kits begin around the high-4k range.

### 64 GB candidate A — Crucial 2×32 GB DDR5-5600 CL46

**Crucial `CT2K32G56C46U5` — 64 GB (2×32 GB), DDR5-5600 CL46**

Why it is attractive:

- ordinary desktop UDIMM;
- 2×32 GB dual-channel topology;
- DDR5-5600 CL46;
- **1.1 V** operating class;
- XMP/EXPO support exists, but the kit can be treated conservatively at Auto/JEDEC settings;
- current broader Romanian pricing is roughly **4.7–4.8k lei** at the low end.

This is currently the **value/control leader** for the optional 64 GB tier if a reputable seller and warranty path are satisfactory.

Reference:
- https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/

### 64 GB candidate B — Kingston FURY Beast 2×32 GB DDR5-5600 CL36 EXPO

**Kingston FURY Beast `KF556C36BBEK2-64` — 64 GB (2×32 GB), DDR5-5600 CL36**

Why it is attractive:

- Kingston explicitly lists this exact kit for the **ASUS ProArt X870E-Creator WiFi**;
- 2×32 GB dual-channel topology;
- AMD EXPO support;
- 5600 MT/s CL36 profile at 1.25 V;
- current PC Garage indexing is around **5.56k lei**.

This is the **compatibility-confidence candidate** if its premium over Crucial becomes small enough.

Reference:
- https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard

### 64 GB candidate C — Kingston FURY Beast 2×32 GB DDR5-6000 CL36 EXPO

**Kingston FURY Beast `KF560C36BBEK2-64` — 64 GB (2×32 GB), DDR5-6000 CL36**

Why it remains on the list:

- Kingston explicitly lists it for the selected ProArt motherboard;
- current PC Garage price indexing has shown approximately **5.0k lei** during this pass, although other current snapshots are materially higher;
- if a real checkout price around 5.0k lei is available, it can be cheaper than nominally slower 5600 kits because of promotions.

Do **not** choose it because of the 6000 MT/s headline. Phase 1 should still boot and validate at Auto/JEDEC first; EXPO is optional. Its value is simply that market promotions can make it the cheapest strongly validated 2×32 GB kit on a given day.

References:
- https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard
- https://www.pricy.ro/ProductUrlId/kit-memorie-ram-kingston-fury-beast-64gb-2x32gb-ddr5-6000mhz-dual-channel-kf560c36bbek2-64-7E9EED5D7E7B74946A9E5225D7780722

### 64 GB control — 1×64 GB Kingston ValueRAM

**Kingston `KVR56U46BD8-64` — 64 GB (1×64 GB), DDR5-5600 CL46, 1.1 V**

Positives:

- Kingston explicitly lists the module for the ProArt X870E-Creator WiFi;
- conservative JEDEC-class 5600 MT/s, CL46, 1.1 V;
- simplest possible one-DIMM topology.

Why it is not currently preferred:

- it remains single-channel;
- current Romanian pricing is roughly **5.1k lei+**, so it costs more than the best 2×32 GB alternatives while delivering less bandwidth.

Keep it only as a procurement/control option if 2×32 GB availability changes materially.

References:
- https://www.kingston.com/en/memory/search/model/110021/asus-proart-x870e-creator-wifi-motherboard
- https://www.price.ro/preturi~kingston-valueram-64gb-ddr5-5600mhz-cl46-1.1v-4734105.html

## Current 32 GB versus 64 GB economics

Using the current 32 GB PC Garage baseline of **2,199.99 lei**:

| Option | Current rough price | Increment vs 32 GB | Capacity/topology |
|---|---:|---:|---|
| GOODRAM `GR5600D564L46/32G` | **~2.20k lei** | baseline | 32 GB, 1×32, single-channel |
| Crucial `CT2K32G56C46U5` | **~4.7–4.8k lei** broader market | **+~2.5–2.6k** | 64 GB, 2×32, dual-channel |
| Kingston `KF560C36BBEK2-64` | **~5.0k lei in recent PC Garage indexing** | **+~2.8k** | 64 GB, 2×32, dual-channel |
| Kingston `KF556C36BBEK2-64` | **~5.56k lei PC Garage** | **+~3.36k** | 64 GB, 2×32, dual-channel |
| Kingston `KVR56U46BD8-64` | **~5.1k lei+ broader market** | **+~2.9k+** | 64 GB, 1×64, single-channel |

These prices are unusually high and volatile. Refresh them immediately before the final order.

### Decision rule for the end-of-build pass

The optional 64 GB tier becomes attractive when the best credible **2×32 GB** kit is close enough to the 32 GB baseline that the extra 32 GB capacity **plus dual-channel bandwidth** justify the additional sunk cost.

Current working threshold:

- **strong buy at ≤ ~4.5k lei** for a credible 2×32 GB kit;
- **serious consideration around ~4.5–4.8k lei**;
- **32 GB baseline remains favored once the 64 GB price moves materially above ~5.0k lei**, unless the final overall build budget has substantial unused room.

This threshold is deliberately not a hard rule. At the final purchase review, consider the whole initial-build total and whether 64 GB would materially delay the 256 GB endpoint.

## Operating policy for either Phase-1 capacity

Regardless of whether the final Phase-1 purchase is 32 GB or 64 GB:

1. install in the motherboard-recommended slot(s);
2. update the ProArt BIOS before serious validation;
3. boot at **Auto/JEDEC** first;
4. treat EXPO/XMP as optional;
5. do not sacrifice stability for advertised frequency/timings;
6. run extended memory testing before commissioning;
7. record exact DIMM SKU and negotiated rate/timings.

## Cooler clearance

- 32 GB GOODRAM baseline: ~31.25 mm high; no NH-D15 G2 front-fan lift required.
- Kingston FURY Beast candidates: ~34.9 mm high; expect only ~3 mm front-fan lift, resulting in ~171 mm cooler height versus the North XL's 185 mm limit.
- GOODRAM IRDM-class 2×32 kits are also around 31.25 mm high, but no exact IRDM SKU is currently preferred over the candidates above.

Therefore none of the serious 64 GB options creates a chassis-clearance problem.

## ECC posture

**System-level ECC remains a strong preference for the eventual 256 GB configuration, but it is not a Phase-1 requirement.**

DDR5 on-die ECC is not equivalent to system-level ECC. For the final memory configuration, prefer ECC UDIMM only if exact 64 GB modules, four-DIMM operation, stability and OS-visible error reporting are all credible.

Do not pay an ECC premium for temporary Phase-1 memory.

## Eventual 256 GB configuration

The endpoint remains **4×64 GB or equivalent**.

At upgrade time:

1. reassess the ProArt BIOS/AGESA and QVL;
2. identify the best exact 4×64 GB configuration then available;
3. prefer ECC UDIMM if exact modules, four-DIMM support, stability and OS-visible reporting are credible;
4. otherwise choose a strongly validated 4×64 GB non-ECC configuration;
5. start at JEDEC/Auto and accept 5200 MT/s or lower if required;
6. avoid EXPO/XMP merely to preserve headline frequency at 256 GB;
7. perform extended stability testing;
8. verify real ECC event reporting if ECC is used.

**RDIMM is incompatible with this AM5 platform.**

## Current conclusion

- **32 GB baseline:** GOODRAM `GR5600D564L46/32G`, 1×32 GB, ~2.20k lei at PC Garage.
- **64 GB optional tier:** prefer **2×32 GB**, with Crucial `CT2K32G56C46U5` as the current value control and Kingston `KF556C36BBEK2-64` / `KF560C36BBEK2-64` as explicitly ProArt-listed alternatives.
- **1×64 GB:** technically valid but currently poor value.
- **Final 32 GB vs 64 GB choice:** **deferred until the end of the initial purchase review**.
- **Long-term endpoint:** 256 GB, expected 4×64 GB; exact modules and ECC verdict deferred.
