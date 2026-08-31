# Case and Airflow Deep Dive

Status: **Selected — Fractal Design North XL Mesh + 3 front intake / 1 rear exhaust**

## Selected chassis

**Fractal Design North XL Mesh** is selected.

It fits the mature system envelope without paying the size/maintenance penalty of an oversized full tower:

- ATX/E-ATX support, including up to 330 mm board width;
- **413 mm GPU length** with the standard front-fan arrangement;
- **185 mm CPU-cooler height**, comfortably above the selected NH-D15 G2 configuration;
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
- **Rear:** **1× Noctua NF-A14x25 G2 PWM — exhaust**
- **Top:** empty initially
- **Side:** empty initially

This creates a direct front-to-rear airflow path and mild positive pressure because the filtered intake capacity exceeds the single rear exhaust.

Do not fill every fan position by default. Additional fans add bearings, noise, dust paths and control complexity. Add top/side fans only if measured thermals justify them.

## Selected rear fan: Noctua NF-A14x25 G2 PWM

Exact selected model:

- **Noctua NF-A14x25 G2 PWM**
- square-frame 140 × 140 × 25 mm version;
- EAN **9010018100617** for the standard brown/beige version;
- 4-pin PWM;
- 0–1500 RPM, with approximately 300 RPM at 20% PWM and stop at 0% PWM;
- maximum airflow about **155.6 m³/h / 91.6 CFM**;
- maximum static pressure about **2.56 mm H2O**;
- SSO2 bearing;
- MTTF **>150,000 hours**;
- six-year manufacturer warranty.

The **chromax.black** version is technically equivalent and may be substituted if it is similarly priced or aesthetically preferred, but there is no reliability or cooling reason to pay a significant premium for the colour variant.

### Why this fan

The rear exhaust is a permanent, low-complexity component in a workstation intended for long ownership. The Noctua premium is acceptable here because it buys:

- an unusually broad useful PWM range rather than a high minimum speed;
- high airflow at modest maximum speed;
- premium bearing/motor construction;
- excellent acoustic efficiency;
- zero-RPM capability if later fan-control policy benefits from it;
- six-year warranty and >150,000-hour MTTF rating;
- consistency with the selected Noctua CPU-cooling ecosystem and long-term serviceability philosophy.

The goal is **not** to run the rear fan at 1500 RPM continuously. It should normally operate at low/moderate RPM and ramp only under sustained thermal load.

### Alternatives considered

**ARCTIC P14 PWM / P14 Max** remain excellent value alternatives. The P14 PWM is substantially cheaper while retaining PWM control and a six-year warranty. The P14 Max adds a 400–2800 RPM range and very high static pressure. Neither displaces the Noctua because maximum fan throughput is not the limiting requirement at the North XL's open rear exhaust; acoustic efficiency, low-speed control and long-term component quality are more valuable here.

The included Fractal Aspect 14 PWM design is adequate for the three front intake positions, where buying three replacement fans would add unnecessary cost. There is no reason to replace them pre-emptively. The single new rear position is where buying the premium fan from the start is cheap and durable.

## Procurement — 2026-08-31

Procurement preference remains **PC Garage first, eMAG second**, but do not buy an unnecessary bundle merely to satisfy retailer preference.

Current Romanian market evidence shows:

- single NF-A14x25 G2 PWM fans roughly in the **180–210 lei** class at competitive sellers;
- PC Garage currently surfaces the **Sx2-PP two-pack** at roughly **388 lei** rather than a clearly indexed single-fan listing.

Because the selected build needs **one** rear fan, do not spend roughly twice the required amount on a two-pack unless the second fan has a concrete planned use. If PC Garage or eMAG has the single fan at purchase time at a normal price, prefer them. Otherwise buy one from a reputable Romanian/EU seller with normal warranty.

## Fan-control policy

- front intake fans: common motherboard-controlled curve where practical;
- rear NF-A14x25 G2 PWM: motherboard-controlled curve;
- prefer low, steady RPM over aggressive reaction to short Ryzen temperature spikes;
- validate using sustained Java build/test workloads and combined CPU/GPU load;
- retain slight positive pressure at normal loads;
- do not use the Low-Noise Adaptor by default; achieve the desired curve through PWM control first.

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

Reopen the chassis/fan decision only if:

- a final component exceeds North XL clearance;
- a selected future GPU requires more than the available length/width/cable clearance;
- the NF-A14x25 G2 PWM becomes unusually expensive or unavailable relative to an equally reliable alternative;
- measured thermals demonstrate that the selected four-fan layout is insufficient; or
- a material reliability/fit issue emerges.

Otherwise, **Fractal Design North XL Mesh + 3× included front intake + 1× Noctua NF-A14x25 G2 PWM rear exhaust is selected**.
