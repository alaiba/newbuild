# Case and Airflow Deep Dive

Status: **Under review / airflow-first chassis strategy selected**

## Scope

The exact case and fan layout remain open.

The governing design principle is closed: prioritize **low-restriction airflow, thermal headroom, dust management, serviceability and future high-power GPU support** over compactness or showcase aesthetics.

The chassis should be treated as a design envelope for the motherboard, cooling, PSU and future GPU path. The exact model remains provisional until those dependencies are sufficiently mature.

## Hard / strong requirements

- ATX support; **E-ATX support strongly preferred** so the motherboard shortlist is not artificially constrained.
- Generous GPU clearance for a future 3.5–4-slot, 500–600 W-class GPU.
- Sufficient GPU width/cable clearance for modern high-power connectors without sharp bending against the side panel.
- High-airflow front intake and unrestricted exhaust path.
- Large, slow fans preferred over many small/high-RPM fans.
- 140 mm fan support preferred where practical.
- Easy-to-remove dust filtration on major intake paths strongly preferred.
- Easy access for cleaning, fan replacement and general service.
- Standard, replaceable fans; avoid dependence on proprietary controllers or integrated electronics where they provide no durable benefit.
- Room for a large air cooler and/or 360/420 mm-class liquid cooling if later justified.
- Space for a long/high-quality ATX PSU with future GPU headroom.
- Good cable-management space, especially around future high-power GPU power connectors.
- Avoid layouts that starve a large GPU against glass, a PSU shroud or another card.
- Good access to M.2 devices and motherboard headers after assembly where practical.
- Front USB-C/high-speed I/O preferred if compatible with the motherboard.
- Robust construction and conventional mechanical design suitable for a roughly 10-year ownership horizon.

## Why airflow matters for reliability

Airflow is not being pursued for benchmark temperature records. It is part of the stability and longevity strategy:

- lower sustained motherboard/VRM temperatures;
- lower SSD controller and NAND temperatures;
- lower GPU component and memory temperatures;
- reduced thermal throttling risk;
- more acoustic headroom because fans can run slower for the same component temperature;
- greater tolerance for normal dust accumulation between maintenance intervals; and
- less avoidable thermal stress over many thousands of operating hours.

Raw airflow must be balanced against dust control. A very open case with no useful intake filtration may cool well when clean but impose a higher long-term maintenance burden.

## Initial August 2026 shortlist

This is a research shortlist only. No case is selected.

### 1. Fractal Design Meshify 3 XL

**Role:** maximum-space / maximum-airflow reference candidate.

Strengths:

- E-ATX, EE-ATX, SSI-EEB and SSI-CEB support;
- GPU clearance up to 512 mm and width up to 189 mm;
- CPU cooler clearance up to 182 mm;
- up to 420 mm top radiator, 360 mm front and side radiators;
- up to ten 140 mm fan positions;
- three 140 mm Momentum fans included;
- spacious cable-management area;
- simple solid-panel version available without RGB or integrated lighting dependence;
- current Romanian pricing appears competitive for the size/class.

Important concern:

- Fractal's official specification lists **only a PSU/bottom dust filter**. The front intake is high-flow mesh rather than a separate removable dust filter. For this build's 10-year maintenance objective, this is a real disadvantage and must be weighed against its excellent airflow and enormous component clearance.

### 2. Fractal Design North XL Mesh

**Role:** balanced airflow / filtration / size candidate.

Strengths:

- E-ATX support;
- front and PSU dust filters;
- ventilated mesh side panel on the Mesh version;
- GPU clearance up to 413 mm;
- CPU cooler clearance up to 185 mm;
- front radiator support up to 420 mm and top support up to 360 mm;
- three 140 mm PWM front fans included;
- substantially smaller internal volume than Meshify 3 XL while retaining generous expansion room;
- strong Romanian availability/pricing.

Potential limitation:

- 413 mm GPU length is generous but materially less than Meshify 3 XL / 7000D headroom. Future GPU width and power-connector clearance must also be checked against the exact card chosen later.

### 3. be quiet! Silent Base 802

**Role:** maintenance / acoustics / configurable-airflow reference candidate.

Strengths:

- interchangeable airflow and sound-damped front/top panels;
- removable front and bottom dust filters;
- E-ATX support up to 305 x 275 mm;
- GPU clearance up to 432 mm without the HDD cage;
- CPU cooler clearance up to 185 mm;
- front radiator support up to 420 mm;
- three 140 mm fans included;
- strong serviceability and relatively low Romanian price.

Potential limitations:

- older platform/design than the newest Fractal candidates;
- E-ATX width support must be checked against any unusually wide motherboard finalist;
- top radiator support is limited to 360 mm.

### 4. Corsair 7000D Airflow

**Role:** oversized full-tower / maximum-expansion control candidate.

Strengths:

- E-ATX support;
- GPU clearance around 450 mm;
- CPU cooler clearance around 190 mm;
- up to 420 mm top radiator and 480 mm front/side-class support;
- extensive fan capacity;
- front dust filtration is available and replaceable;
- exceptionally large working volume for future high-power GPU and complex cooling.

Potential limitations:

- very large and heavy;
- materially more expensive in Romania than the other current candidates;
- likely more case than this system actually needs unless later motherboard/GPU/cooling choices justify the volume.

## Initial direction

The first-pass comparison suggests that **Meshify 3 XL, North XL Mesh and Silent Base 802** deserve detailed evaluation. Corsair 7000D Airflow remains a useful upper-bound size/expansion reference.

The most important unresolved trade-off is not raw airflow; it is:

**maximum open airflow and component clearance vs. filtered intake, maintenance burden, size and long-term serviceability.**

Do not choose Meshify 3 XL merely because it has the largest clearances. Its lack of a dedicated front dust filter is a material negative under the current reliability/maintenance philosophy.

## Review focus

- motherboard form-factor support and exact board width
- selected CPU-cooler clearance
- existing RTX 3060 fit
- future 3.5–4-slot / long GPU headroom
- future GPU width and power-cable bend clearance
- airflow path and restriction
- intake filtration efficiency and pressure drop
- dust accumulation and cleaning procedure
- acoustic behavior at realistic workstation fan speeds
- front I/O
- storage mounting requirements if any
- fan placement and header/control requirements
- cable-management quality
- build/serviceability
- filter and fan accessibility
- replacement-part availability
- long-PSU clearance
- Romanian/EU pricing/value

## Required output

Finish with:

1. case requirements derived from selected/provisional motherboard, cooling, storage and PSU;
2. serious candidate shortlist;
3. provisional chassis target;
4. final exact case recommendation only after dependent components are sufficiently mature;
5. fan layout;
6. clearance validation for current and future GPU scenarios;
7. front-I/O/header dependencies;
8. maintenance and dust-management plan;
9. Romanian price/value;
10. promotion gates for moving the chassis from provisional target to selected.
