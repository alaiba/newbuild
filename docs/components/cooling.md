# Cooling Deep Dive

Status: **High-end air cooling selected / exact cooler selected**

## Decision

For the Ryzen 9 9950X3D build, use **high-end air cooling** with the:

- **Noctua NH-D15 G2 — standard medium-convexity base**
- installed using the included **7 mm AM5 offset mounting position**

The previously preferred **NH-D15 G2 LBC** is no longer the selected variant. It remains technically excellent on AM5, but it does not provide a meaningful advantage for this build once the standard G2 is installed with Noctua's offset mount.

Keep one liquid fallback only:

- **ARCTIC Liquid Freezer III Pro 360** — use only if measured sustained workloads later demonstrate an unacceptable thermal/acoustic result with the selected air cooler

The 420 mm ARCTIC remains outside the target architecture.

## Why air cooling wins for this workstation

The build prioritizes stability, serviceability and a roughly 10-year useful-life objective over overclocking or benchmark-maximizing behavior.

For that objective, a top-tier tower cooler has several durable advantages:

- no pump as an additional wear/failure item;
- no coolant, tubing or seals to age;
- the heatsink itself has essentially no active failure mode;
- standard replaceable fans are the primary wear components;
- fan degradation/failure is obvious and easily serviced;
- no radiator placement dependency that can distort front intake or future-GPU airflow;
- lower long-term complexity while still providing enough cooling for stock/conservative 9950X3D operation.

This does **not** mean liquid cooling is unreliable or inappropriate. It means its extra thermal headroom is not currently valuable enough to outweigh the additional active/mechanical complexity for this particular stability-first build.

## Why standard NH-D15 G2 wins over NH-D15 G2 LBC

Noctua currently recommends the **standard NH-D15 G2** as the best all-rounder and most versatile of the three base-convexity variants.

For AMD AM5 specifically:

- the standard G2 includes a **7 mm offset mounting option** that shifts the cooler toward the CCD hotspot;
- Noctua states that the standard version provides **excellent** AM5 performance when used with this offset;
- Noctua's own comparison reports the **best absolute AM5 results** from the standard medium-convexity base with the included offset mount;
- the LBC version is mainly advantageous on AM5 **without** the offset mount, or for unusually flat/lapped/direct-die configurations;
- with offset mounting, LBC is effectively on par and may only edge the standard model by a few tenths in some cases;
- the standard base retains better versatility for future sockets and other CPU heat-spreader geometries.

For a workstation intended to last around a decade, that broader future-socket flexibility is more valuable than optimizing around a specialized LBC geometry that does not improve the selected AM5 installation in a material way.

Sources:
- https://www.noctua.at/en/support/faqs/which-version-of-the-nh-d15-g2-should-i-buy-lbc-standard-or-hbc
- https://www.noctua.at/en/expertise/tech/nh-d15-g2-versions-heatsink-contact-quality-optimisation-explained
- https://www.noctua.at/en/products/nh-d15-g2/features

## 9950X3D thermal evidence

GamersNexus' 2025 AM5 cooler suite used Ryzen 9 9950X3D loads up to 276 W. In its harsh 9950X3D noise-normalized test, the NH-D15 G2 was the only air cooler in the tested set able to complete the test without throttling or a thermal trip.

That test is materially harsher than the operating point selected here. This build will run the 9950X3D at stock/conservative settings and explicitly **will not enable PBO/uncapped power merely because thermal headroom exists**.

A separate 2026 9950X3D test of the G2 family around stock-class package power showed substantially easier thermals than the 276 W torture condition, reinforcing that a top-tier air cooler is an appropriate fit for the intended workload.

Sources:
- https://gamersnexus.net/coolers/best-cpu-coolers-weve-tested-2025-thermals-noise-levels-value-26-coolers-tested
- https://www.thelab.gr/reviews/heatsinks-coolers-watercooling-reviews/noctua-nh-d15-g2-g2-lbc-review-%CE%B7-%CE%B5%CF%80%CE%B9%CF%83%CF%84%CF%81%CE%BF%CF%86%CE%AE-%CF%84%CE%BF%CF%85-%CE%B2%CE%B1%CF%83%CE%B9%CE%BB%CE%B9%CE%AC-%CE%BC%CE%B5-%CE%B4%CF%8D%CE%BF-%CF%80%CF%81%CF%8C%CF%83%CF%89%CF%80%CE%B1-r943/

## Selected cooler specifications

Relevant manufacturer specifications for the standard NH-D15 G2:

- AMD AM5 support;
- 168 mm stock total height;
- dual 140 mm NF-A14x25r G2 PWM fans;
- eight heatpipes;
- NSPR 228;
- six-year warranty;
- SecuFirm2+ multi-socket mounting system;
- 7 mm AMD AM5 offset mounting option;
- long-running Noctua mounting-kit ecosystem for future sockets when technically possible.

Sources:
- https://www.noctua.at/en/products/nh-d15-g2/specifications
- https://www.noctua.at/en/products/nh-d15-g2/features

## Motherboard compatibility

The **ASUS ProArt X870E-Creator WiFi** is explicitly listed as compatible with the NH-D15 G2 by Noctua.

No motherboard-heatsink or PCIe-slot conflict is expected for the selected orientation. The G2 heatsink is designed with an offset geometry that improves top-PCIe-slot clearance relative to the original D15 generation.

Source:
- https://www.noctua.at/en/compatibility/by-components/motherboards/asus-proart-x870e-creator-wifi

## RAM clearance with selected Phase-1 GOODRAM

The selected Phase-1 RAM is:

- **GOODRAM 32 GB DDR5-5600 CL46**
- exact SKU: **`GR5600D564L46/32G`**
- topology: 1×32 GB
- module height: approximately **31.25 mm**

The NH-D15 G2 provides roughly **32 mm RAM clearance** in the normal dual-fan configuration.

Therefore:

- the selected module fits below the front fan without lifting it;
- practical cooler height remains the stock **168 mm**;
- no airflow/acoustic compromise is introduced by the Phase-1 memory choice.

The eventual 256 GB memory remains unknown. If future 64 GB DIMMs are taller than the cooler's normal clearance, the front fan may need to be raised or the fan arrangement reconsidered then.

Sources:
- https://www.goodram.com/produkty/goodram-ddr5-dimm/
- https://www.noctua.at/en/support/faqs/what-is-the-ram-clearance-of-my-noctua-cpu-cooler

## Case clearance: Fractal Design North XL Mesh

The selected **Fractal Design North XL Mesh** supports CPU coolers up to **185 mm** high.

With the selected Phase-1 GOODRAM:

- NH-D15 G2 stock height: **168 mm**;
- required front-fan lift: **none**;
- resulting practical height: **168 mm**;
- remaining case margin: approximately **17 mm**.

This is comfortably inside the chassis envelope and leaves generous tolerance for ordinary assembly variation.

Source:
- https://www.fractal-design.com/products/cases/north/north-xl/mesh/

## Procurement comparison: standard vs LBC

Procurement preference for the cooler is:

1. **PC Garage** first;
2. **eMAG** second;
3. other reputable Romanian/EU retailers only if both preferred sources are materially unattractive.

Current Romanian indexing confirms the standard NH-D15 G2 remains locally available, including PC Garage references. Search/indexed pricing for exact LBC versus standard listings is inconsistent enough that the decision should not rely on a few-lei snapshot.

The rule is therefore simple:

- buy the **standard NH-D15 G2**;
- do **not** pay a material premium for LBC;
- even if LBC happens to be slightly cheaper, standard remains preferred unless the price difference becomes large enough to outweigh the future-versatility advantage;
- immediately before checkout, compare PC Garage and eMAG and prefer PC Garage when the difference is small.

This choice is technical first, retailer second: the standard base is the better long-horizon fit even before price is considered.

## Why pay the Noctua premium

The NH-D15 G2 is not the cheapest technically adequate cooler. The premium buys durable characteristics rather than benchmark prestige:

- flagship-class air-cooling margin for the 9950X3D;
- excellent noise-normalized behavior;
- premium replaceable fans;
- mature mounting hardware;
- six-year warranty;
- broad socket support and future mounting-kit policy;
- a heatsink body that can plausibly remain in service across multiple fan replacements and potentially future platforms.

That profile matches the selected stability-first, long-service-life design better than choosing purely on price/performance.

## Liquid fallback: ARCTIC Liquid Freezer III Pro 360

If real validation later shows that the NH-D15 G2 is materially inadequate for sustained development workloads at the desired acoustic target, the fallback remains the **ARCTIC Liquid Freezer III Pro 360**.

Reasons:

- direct strong 9950X3D testing;
- six-year warranty;
- substantially greater extreme-load thermal headroom;
- top 360 mm placement is compatible with the North XL architecture and preserves direct front GPU intake.

However, the AIO introduces pump/liquid dependencies that are intentionally avoided unless measurements show a real need.

The 420 mm version remains rejected because its small advantage around stock-class CPU power does not justify the additional radiator-placement and airflow constraints.

## Fan-control strategy

For the selected air-cooled configuration:

- run the CPU at stock/conservative power settings;
- use a smooth fan curve rather than chasing transient Ryzen temperature spikes;
- allow the two CPU fans to ramp meaningfully only under sustained temperature/load;
- avoid unnecessarily running 140 mm fans at maximum RPM during ordinary IDE/build bursts;
- validate the final curve with sustained compilation/test workloads, not just synthetic stress tests.

No manual overclock/PBO policy should be adopted to exploit unused thermal margin. Additional cooling headroom is for **lower temperature, lower noise and greater environmental margin**, not higher power consumption.

## Installation policy

At assembly:

1. confirm the cooler is the **standard NH-D15 G2**, not LBC/HBC;
2. use Noctua's **-7 mm AM5 offset mounting position**;
3. apply NT-H2 using Noctua's current AM5 guidance;
4. install the center fan normally;
5. keep the front fan at the normal stock position with the selected 31.25 mm GOODRAM DIMM;
6. confirm the fan remains comfortably inside the North XL side-panel envelope;
7. inspect top-PCIe-slot/GPU and EPS-cable clearance before final cable management.

## Bring-up validation

After assembly:

- verify both CPU fans report RPM and respond to PWM control;
- run a sustained CPU workload representative of long Java/test/build activity;
- run a synthetic CPU thermal test as a separate worst-case check;
- log CPU package temperature, CCD temperatures, clocks and fan RPM;
- confirm no thermal throttling at the selected stock/conservative power policy;
- tune the fan curve for sustained loads and transient-spike tolerance;
- repeat combined CPU/GPU thermal testing with the case closed.

The target is not the lowest possible benchmark temperature. The target is **stable sustained operation with comfortable thermal margin and acceptable acoustics**.

## Long-term maintenance

For the selected air architecture:

- clean heatsink fins during normal case dust maintenance;
- inspect fan bearings/noise periodically;
- replace fans individually if they degrade;
- inspect mounting pressure and repaste when the cooler is removed or when sustained temperatures materially drift upward;
- retain mounting hardware and documentation with the system.

There is no requirement to replace the heatsink on a schedule.

## Selected conclusion

> **Ryzen 9 9950X3D + Noctua NH-D15 G2 standard + 7 mm AM5 offset mount + Fractal North XL Mesh, operated at stock/conservative CPU settings.**

With the selected Phase-1 GOODRAM DIMM, the cooler requires no fan lift and remains at its stock 168 mm height.

This exact cooler decision is closed. Reopen it only if a material compatibility/availability problem appears or real workload validation demonstrates that the selected acoustic/thermal target cannot be met.
