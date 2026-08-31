# Case and Airflow Deep Dive

Status: **Selected — be quiet! Pure Base 501 Airflow Black `BG074`**

## Selected chassis

Use **be quiet! Pure Base 501 Airflow Black `BG074`**.

Relevant envelope for this workstation:

- ATX or smaller motherboard;
- approximately **368 mm GPU clearance**;
- approximately **178 mm CPU-cooler clearance**;
- two included **140 mm PWM fans**;
- practical support for two 3.5-inch HDDs for later cold storage;
- dimensions approximately **450 × 231 × 463 mm**.

Manufacturer reference:
- https://www.bequiet.com/en/case/5322

## Why it replaces North XL

The previous North XL selection was driven partly by requirements that no longer exist:

- provisioning for a very large 500–600 W future GPU;
- preserving NH-D15 G2-class cooler clearance;
- broader E-ATX/workstation expansion headroom.

The current build needs one normal discrete GPU, an ATX-or-smaller motherboard, a compact high-performance air cooler and modest additive storage.

Pure Base 501 therefore provides enough useful room while avoiding roughly 20 L of unnecessary chassis volume and a substantial price premium.

## Cooler fit

Selected cooler: **Thermalright Phantom Spirit 120 standard**.

- cooler height: approximately **157 mm**;
- case limit: approximately **178 mm**;
- nominal vertical margin: approximately **21 mm**.

This leaves useful tolerance for RAM/front-fan positioning and assembly variation.

## GPU policy

The selected 368 mm GPU-length envelope is intentionally not sized around an unknown future flagship.

- current RTX 3060 is the intended GPU for as long as it remains useful/reliable;
- if a future replacement fits, no chassis change is needed;
- if a future GPU genuinely requires a larger chassis, reconsider the case at that upgrade rather than carrying unused volume for years.

## Selected fan layout

Initial layout uses **only the two included 140 mm PWM fans**:

- **front:** 1×140 mm intake;
- **rear:** 1×140 mm exhaust;
- additional front/top fans: none initially.

Do not purchase a dedicated Noctua rear fan. The previous NF-A14x25 G2 purchase target is superseded.

## Why only two fans initially

The current heat load is modest relative to the chassis capability:

- stock/conservative 9950X3D;
- RTX 3060 12 GB;
- no planned 500–600 W GPU;
- no overclocking objective.

Additional fans should be driven by measurements, not slot count. If closed-case validation shows higher-than-desired CPU/GPU/VRM/SSD temperatures or fan noise, the **first** airflow upgrade is one additional 140 mm front intake.

## Fan-control policy

- front and rear case fans: motherboard-controlled PWM curves where practical;
- prefer low/steady RPM over aggressive response to short Ryzen temperature spikes;
- validate with sustained Java build/test workloads and combined CPU/GPU activity;
- tune for temperatures and acoustics together.

## Dust and maintenance

- inspect/clean case filters and mesh according to observed dust accumulation;
- clean cooler/GPU fins and fan blades when visible buildup appears;
- do not use higher fan speed as a substitute for cleaning;
- record a clean-system thermal baseline after assembly.

## Storage/serviceability

The case preserves enough conventional storage for the simplified storage policy:

- fast active work remains on CPU-direct NVMe;
- system drive can be NVMe or SATA;
- up to two 3.5-inch HDD positions can serve later cold/archive storage if useful.

This is sufficient; the build does not require a large storage chassis.

## Reopen conditions

Reopen chassis/airflow only if:

- the final motherboard exceeds ATX;
- the exact RAM/cooler combination cannot fit within the 178 mm envelope;
- a future selected GPU actually exceeds the available physical clearance;
- measured closed-case thermals/acoustics show the chassis itself is inadequate;
- exact `BG074` becomes unavailable or materially overpriced before purchase.

Otherwise:

> **be quiet! Pure Base 501 Airflow Black `BG074` + its two included 140 mm PWM fans is the selected chassis/initial-airflow configuration.**
