# Case and Airflow Deep Dive

Status: **Selected — Fractal Design North XL Mesh**

## Selected chassis

**Fractal Design North XL Mesh** is selected.

It fits the mature system envelope without paying the size/maintenance penalty of an oversized full tower:

- ATX/E-ATX support, including up to 330 mm board width;
- **413 mm GPU length** with the standard front-fan arrangement;
- **185 mm CPU-cooler height**, comfortably above the 168 mm NH-D15 G2 target;
- dedicated **front and PSU dust filters**;
- three included **140 mm PWM front intake fans**;
- rear 140 mm fan support;
- top 360 mm radiator support if liquid cooling is ever needed later;
- 290 mm PSU clearance, far beyond the 160 mm provisional Seasonic PSU;
- 20 Gbps front USB-C;
- approximately **503 × 240 × 509 mm**, 57.62 L and 9.7 kg.

## Why North XL wins

### Versus Fractal Meshify 3 XL

Meshify 3 XL provides substantially more GPU clearance — roughly 512 mm — and more total expansion volume. That headroom is not required for the selected single-GPU AM5 architecture.

Its main disadvantage here is maintenance: Fractal's official specification lists only a **PSU dust filter**, whereas North XL provides a dedicated front filter. Meshify 3 XL is also materially larger at roughly 71.29 L.

For a long-lived workstation, North XL provides enough expansion while avoiding unnecessary size and dust-management burden.

### Versus be quiet! Silent Base 802

Silent Base 802 remains a credible alternative with 432 mm GPU clearance, 185 mm CPU-cooler clearance, strong filtration and three included 140 mm fans.

However, it is an older, larger/wider design and no longer gains an important advantage from 420 mm front-radiator support because high-end air cooling is selected and 420 mm liquid support is explicitly unnecessary.

### Versus Corsair 7000D Airflow

7000D provides roughly 450 mm GPU clearance and enormous expansion capacity, but is over 80 L and about 20.7 kg. That is excessive for the intended single-GPU AM5 workstation.

## Future GPU fit policy

The selected design envelope remains **one very large 500–600 W-class GPU**.

North XL provides:

- 413 mm card-length clearance with the normal front fans;
- on the Mesh version, up to roughly **192 mm total GPU width including connector/cabling** with the side fan bracket in the high position;
- no planned front radiator, so GPU length is not reduced by radiator thickness.

The eventual GPU must still be checked explicitly for card length, width/thickness, 12V-2x6 connector position and side-panel cable-bend clearance.

If a future card genuinely exceeds this envelope, reconsidering the chassis at that future GPU purchase is preferable to oversizing today's workstation around an unknown card.

## Selected fan layout

### Initial layout

- **Front:** 3× included Fractal Aspect 14 PWM — intake
- **Rear:** add 1× 140 mm PWM — exhaust
- **Top:** empty initially
- **Side:** empty initially

This creates a direct front-to-rear airflow path and mild positive pressure because the filtered intake capacity exceeds the single rear exhaust.

Do not fill every fan position by default. Additional fans add bearings, noise, dust paths and control complexity. Add top/side fans only if measured thermals justify them.

### Preferred rear fan

**Noctua NF-A14x25 G2 PWM** is the provisional premium rear exhaust fan.

Relevant manufacturer specifications:

- 140 × 140 × 25 mm;
- 0–1500 rpm PWM;
- maximum airflow about 91.6 CFM;
- 6-year warranty;
- MTTF >150,000 hours.

A lower-cost quality 140 mm PWM fan is acceptable if the Noctua premium is disproportionate at purchase time.

## Fan-control policy

- front intake fans: common motherboard-controlled curve where practical;
- rear exhaust: motherboard-controlled curve;
- prefer low, steady RPM over aggressive reaction to short Ryzen temperature spikes;
- validate using sustained Java build/test workloads and combined CPU/GPU load;
- retain slight positive pressure at normal loads.

## Dust and maintenance

North XL's dedicated front and PSU filters are material reasons for selection.

Maintenance policy:

- inspect/clean front filter according to observed dust accumulation;
- inspect PSU filter at the same interval;
- clean heatsinks/fan blades when visible buildup appears;
- do not use higher fan speed as a substitute for cleaning;
- record a clean-system thermal baseline after assembly.

## Current Romanian price position — August 2026

Recent Romanian listings put North XL Mesh around **925–1,060 lei** depending on retailer and stock.

For comparison:

- Silent Base 802: roughly **804–900 lei**;
- Meshify 3 XL: roughly **1,100–1,350 lei** depending version/stock;
- Corsair 7000D: materially more expensive and much larger.

The North XL premium over Silent Base 802 is modest and buys a newer, smaller package with the filtration, cooler clearance and GPU envelope the build actually needs.

## Reopen conditions

Reopen the chassis decision only if:

- the final motherboard exceeds North XL board-width support;
- the final cooler/RAM combination cannot fit within the 185 mm cooler-height envelope;
- a selected GPU requires more than the available length/width/cable clearance;
- purchase-time pricing/availability changes radically; or
- a material reliability/fit issue emerges.

Otherwise, **Fractal Design North XL Mesh is selected**.