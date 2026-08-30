# Cooling Deep Dive

Status: **High-end air cooling selected / exact cooler provisional**

## Decision

For the Ryzen 9 9950X3D build, use **high-end air cooling as the selected cooling architecture**.

The current provisional cooler target is:

- **Noctua NH-D15 G2 LBC** — preferred AM5-specific air-cooling target

Keep these live alternatives:

- **Noctua NH-D15 G2 standard** — near-equivalent fallback if it is materially easier/cheaper to source; use the included AM5 7 mm offset mount
- **ARCTIC Liquid Freezer III Pro 360** — liquid-cooling fallback if later validation shows that sustained real development workloads need materially more thermal/acoustic headroom than the air cooler provides

The 420 mm ARCTIC is **not a current target**. It is useful as an upper-bound cooling reference, but its small advantage over the best 360 mm AIOs at roughly stock Ryzen power does not justify the additional chassis/radiator-fit constraints for this build.

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

## 9950X3D thermal evidence

### High-end air

GamersNexus' 2025 AM5 cooler suite used Ryzen 9 9950X3D loads up to 276 W. In its 9950X3D noise-normalized test, the NH-D15 G2 was the **only air cooler in the tested set able to complete the harsh test without throttling or a thermal trip**, although it was near 90 C once ambient was included. GN also found the **LBC variant best on AMD** among the D15 G2 base variants.

Source:
- https://gamersnexus.net/coolers/best-cpu-coolers-weve-tested-2025-thermals-noise-levels-value-26-coolers-tested

A 2026 independent test on an actual 9950X3D measured the NH-D15 G2 LBC at about **73.9 C plateau temperature around 198 W package power** in Cinebench 2026, illustrating that the cooler has a materially easier job at approximately stock-class sustained power than in GN's 276 W torture case.

Source:
- https://www.thelab.gr/reviews/heatsinks-coolers-watercooling-reviews/noctua-nh-d15-g2-g2-lbc-review-%CE%B7-%CE%B5%CF%80%CE%B9%CF%83%CF%84%CF%81%CE%BF%CF%86%CE%AE-%CF%84%CE%BF%CF%85-%CE%B2%CE%B1%CF%83%CE%B9%CE%BB%CE%B9%CE%AC-%CE%BC%CE%B5-%CE%B4%CF%8D%CE%BF-%CF%80%CF%81%CF%8C%CF%83%CF%89%CF%80%CE%B1-r943/

The design should therefore **not enable PBO/uncapped power merely because additional cooling headroom exists**. Stock/conservative operation remains the baseline.

### Liquid-cooling upper bound

Tom's Hardware tested the **ARCTIC Liquid Freezer III Pro 360 directly on the 9950X3D** and found it capable of handling the CPU even with PBO enabled. The cooler is substantially more capable thermally than air when power is allowed to rise aggressively.

Source:
- https://www.tomshardware.com/pc-components/liquid-cooling/arctic-liquid-freezer-iii-pro-review

For the 420 mm version, Tom's Hardware found only about a **0.9 C advantage over the best tested 360 mm AIO at roughly 200 W**. That makes the 420 mm unit unattractive for this build unless a later requirement specifically demands maximum liquid-cooling capacity.

Source:
- https://www.tomshardware.com/pc-components/liquid-cooling/arctic-liquid-freezer-iii-pro-420-review/2

## Provisional target: Noctua NH-D15 G2 LBC

Relevant manufacturer specifications:

- AM5 support
- 168 mm total height
- dual 140 mm NF-A14x25r G2 PWM fans
- eight heatpipes
- 6-year warranty
- fan MTTF >150,000 hours
- AM5 offset mounting option
- LBC coldplate specifically intended for relatively flat CPUs such as AM5
- standard mounting ecosystem with Noctua's long-running practice of offering future-socket mounting kits when technically possible

Sources:
- https://www.noctua.at/en/products/nh-d15-g2-lbc/specifications
- https://www.noctua.at/en/products/nh-d15-g2-lbc/features

### Why pay the Noctua premium

The NH-D15 G2 is not the best price/performance air cooler. GamersNexus explicitly notes that substantially cheaper coolers can land within a few degrees.

For this build, however, the premium buys durable characteristics rather than benchmark prestige:

- best-in-class air performance on the tested 9950X3D suite;
- strong noise-normalized behavior;
- AM5-specific coldplate/mounting optimization;
- mature mounting hardware;
- premium replaceable fans;
- long manufacturer support/mount ecosystem;
- six-year warranty;
- a cooler body that can plausibly remain useful through multiple fan replacements and potentially future sockets.

Current Romanian pricing for the standard NH-D15 G2 is roughly **640–850 lei**, with competitive offers around 700 lei. The LBC variant may require wider EU sourcing and should not command an excessive premium over the standard model.

Romanian price reference:
- https://www.compari.ro/coolere-c3094/noctua/nh-d15-g2-p1101386203/

If the LBC variant is difficult to source or materially overpriced, use the **standard NH-D15 G2 with the included 7 mm AM5 offset mounting** rather than paying a large premium for a small coldplate-geometry gain.

## Value-control air cooler

The **Thermalright Phantom Spirit 120 SE** remains a useful budget-control reference at roughly **200–250 lei** in Romania.

It demonstrates how much of the Noctua price is premium engineering/support rather than simple heat dissipation. However, this workstation does not need to minimize cooler purchase price, and the NH-D15 G2's superior 9950X3D noise-normalized margin, service ecosystem and long-horizon support are worth the modest absolute premium in the context of the complete machine.

Price reference:
- https://www.compari.ro/coolere-c3094/thermalright/phantom-spirit-120-se-p1005219121/

Do not replace the Noctua provisional target with the Thermalright merely to save approximately 500 lei unless final budget pressure makes that saving meaningful.

## Liquid fallback: ARCTIC Liquid Freezer III Pro 360

If later thermal validation shows air cooling is materially inadequate for our real sustained workload, prefer the **360 mm** ARCTIC over the 420 mm model.

Reasons:

- directly demonstrated excellent 9950X3D performance;
- six-year warranty;
- strong noise-normalized thermal performance when fan/pump curves are controlled sensibly;
- about **375–475 lei** in current Romanian listings, so liquid cooling is not being rejected because of price;
- 398 x 120 x 38 mm radiator, requiring roughly 63 mm total radiator/fan clearance;
- fits the **top 360 mm radiator envelope shared by North XL Mesh, Silent Base 802 and Meshify 3 XL**, preserving direct front intake for a future high-power GPU.

Sources:
- https://www.arctic.de/en/Liquid-Freezer-III-Pro-360/ACFRE00180A
- https://www.compari.ro/coolere-c3094/arctic/cooler-liquid-freezer-iii-pro-360-acfre00180a-p1193101027/

AIO use would require explicit validation of motherboard M.2-heatsink/block clearance because ARCTIC notes limited compatibility with some motherboards that have oversized M.2_1 heatsinks.

## Why not 420 mm

The ARCTIC Liquid Freezer III Pro 420 is an excellent cooler, but it is a poor architectural fit for the current build:

- 458 x 138 x 38 mm radiator plus 27 mm fans creates a roughly 65 mm-thick assembly;
- North XL Mesh and Silent Base 802 support 420 mm radiators primarily at the **front**, where the radiator would reduce the cleanest direct-air path and may reduce practical future-GPU clearance;
- Meshify 3 XL can support a 420 mm radiator at the top, but choosing the exact chassis around a marginal 420-vs-360 cooling gain would be backwards;
- at around 200 W, independent testing showed less than a 1 C lead over the best 360 mm AIO.

Therefore **do not let 420 mm radiator support drive the case decision**.

## Clearance implications

### Case

NH-D15 G2 height is **168 mm**.

All current serious chassis candidates clear it nominally:

- North XL Mesh: 185 mm CPU-cooler clearance
- Silent Base 802: 185 mm
- Meshify 3 XL: 182 mm
- Corsair 7000D: about 190 mm

This means the selected air-cooling architecture does not eliminate any current chassis finalist.

### Memory

The NH-D15 G2 provides:

- about **32 mm RAM clearance in normal dual-fan configuration**;
- at least 59 mm in single-fan mode;
- more dual-fan RAM clearance by raising the front fan, at the cost of equal additional total cooler height.

Source:
- https://www.noctua.at/en/support/faqs/what-is-the-ram-clearance-of-my-noctua-cpu-cooler

Because the current cases provide 14–17 mm of nominal height margin over the stock 168 mm cooler height, moderate fan raising is possible. Nevertheless, the eventual 256 GB memory review should strongly prefer **low-profile ECC/JEDEC UDIMMs** when technically equivalent, both for cooler clearance and for a simpler airflow path.

### Motherboard / PCIe

The G2 heatsink is offset toward the upper motherboard edge to improve top-PCIe-slot clearance. Exact compatibility with the final ProArt/Taichi Creator + RAM configuration must still be checked before purchase.

## Fan-control strategy

For the air-cooled configuration:

- run the CPU at stock/conservative power settings;
- use a smooth fan curve rather than chasing transient Ryzen temperature spikes;
- allow the two CPU fans to ramp meaningfully only under sustained temperature/load;
- avoid unnecessarily running 140 mm fans at maximum RPM during ordinary IDE/build bursts;
- validate the final curve with sustained compilation/test workloads, not just synthetic stress tests.

No manual overclock/PBO policy should be adopted to exploit unused thermal margin. Additional cooling headroom is for **lower temperature, lower noise and greater environmental margin**, not higher power consumption.

## Long-term maintenance

For the selected air architecture:

- clean heatsink fins during normal case dust maintenance;
- inspect fan bearings/noise periodically;
- replace fans individually if they degrade;
- inspect mounting pressure and repaste when the cooler is removed or when sustained temperatures materially drift upward;
- retain mounting hardware and documentation with the system.

There is no requirement to replace the heatsink on a schedule.

## Promotion gate for the exact cooler

Promote **NH-D15 G2 LBC** from provisional target to Selected only after:

1. exact motherboard compatibility is confirmed;
2. exact initial RAM and eventual 256 GB RAM height/clearance are known;
3. selected chassis provides adequate cooler/fan-raised height clearance;
4. current LBC price/availability is reasonable relative to the standard G2;
5. no new 9950X3D-specific evidence shows an unacceptable sustained thermal/acoustic limitation at stock/conservative settings.

If those checks pass, the expected final cooling architecture is:

> **Ryzen 9 9950X3D + Noctua NH-D15 G2 LBC + airflow-first chassis, operated at stock/conservative CPU settings.**
