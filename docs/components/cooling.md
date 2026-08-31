# Cooling Deep Dive

Status: **Selected — Thermalright Phantom Spirit 120 standard**

## Decision

Use the **Thermalright Phantom Spirit 120**, standard model, on the Ryzen 9 9950X3D.

The CPU remains stock/conservative. The objective is sustained stability and acceptable acoustics under long Java/Gradle/Maven/test workloads, not maximum benchmark cooling capacity.

Do **not** silently substitute Phantom Spirit 120 SE, EVO or another variant. Any variant change must be reviewed for dimensions, fans, acoustics, price and mounting.

## Why air cooling remains correct

The workstation prioritizes long service life and simple maintenance:

- no pump as an additional wear item;
- no coolant/tubing/seals;
- passive heatsink body has little to fail;
- standard fans are individually replaceable;
- simple diagnosis and maintenance;
- no radiator-placement constraints.

Liquid cooling remains a fallback only if real measurements later show that this air-cooling approach cannot meet the desired thermal/acoustic target.

## Why Phantom Spirit 120 wins

The previous NH-D15 G2 selection was made when the build carried more speculative thermal/chassis headroom. After removing the 500–600 W future-GPU assumption and reopening the case, maximum air-cooling capacity no longer justified the additional cost and size.

The Phantom Spirit 120 provides the relevant characteristics:

- AM5 support;
- dual-tower layout;
- seven 6 mm heatpipes;
- two 120 mm PWM fans;
- approximately **157 mm total height**;
- strong high-load air-cooling performance in independent testing;
- much lower purchase cost than NH-U12A/NH-D15 G2-class premium coolers.

Manufacturer reference:
- https://www.thermalright.com/product/phantom-spirit-120/

Independent reference:
- https://www.tomshardware.com/reviews/thermalright-phantom-spirit-120-review

## Case fit

Selected chassis: **be quiet! Pure Base 501 Airflow Black `BG074`**.

Relevant geometry:

- case CPU-cooler limit: approximately **178 mm**;
- Phantom Spirit 120 height: approximately **157 mm**;
- nominal vertical margin: approximately **21 mm**.

This is materially more forgiving than the previous NH-D15 G2 + regular-Fractal-North concept.

## RAM interaction

Final memory remains **2×64 GB / 1DPC** and exact DIMM height is still open.

The front cooler fan can interact with taller DIMMs. The final RAM selection must therefore confirm:

- DIMM height;
- front-fan position/lift if required;
- total resulting cooler height remains below the case limit;
- no interference with motherboard heatsinks or the first GPU slot.

Because the chassis provides roughly 21 mm of nominal height margin, moderate fan lift is acceptable without forcing unusually short DIMMs. RAM electrical stability/value remains more important than decorative heat-spreader height.

## Why not NH-U12A

The NH-U12A remains an excellent compact premium cooler with strong Noctua mounting/support/fan quality.

It loses because its substantial price premium does not buy a material workload benefit after the Phantom Spirit already satisfies the expected stock/conservative thermal requirement. The Noctua ecosystem is valuable, but not enough here to outweigh the difference in utility per leu.

## Why not NH-D15 G2

The NH-D15 G2 remains the maximum-air-cooling reference and has excellent acoustics, mounting and serviceability.

It is no longer selected because:

- its extra thermal capacity is not required by the chosen CPU operating policy;
- it is materially more expensive;
- its larger physical envelope creates more RAM/case interaction;
- preserving it would encourage unnecessary chassis oversizing.

## Fan-control strategy

- keep CPU stock/conservative;
- use a smooth PWM curve rather than chasing short Ryzen temperature spikes;
- tune against sustained development workloads;
- validate with a separate synthetic thermal test;
- do not increase CPU power limits merely because thermal headroom exists.

## Bring-up validation

After assembly:

1. verify both cooler fans report RPM and respond to PWM control;
2. run a sustained representative Java/test/build workload;
3. run a synthetic CPU thermal test separately;
4. log package/CCD temperatures, clocks and fan RPM;
5. confirm no material thermal throttling under the selected stock/conservative policy;
6. tune the fan curve for acceptable sustained noise;
7. repeat with the case closed and combined CPU/GPU activity.

If closed-case thermals are higher than desired, first test adding a second front case intake before replacing the CPU cooler.

## Long-term maintenance

- clean fins during normal dust maintenance;
- inspect fan bearings/noise periodically;
- replace individual fans if they degrade;
- repaste when the cooler is removed or sustained temperatures materially drift;
- retain AM5 mounting hardware/documentation.

## Selected conclusion

> **Ryzen 9 9950X3D + Thermalright Phantom Spirit 120 standard, operated stock/conservatively.**

This exact cooler is selected. Reopen only for a material availability/compatibility issue or if real workload validation shows the thermal/acoustic target is not being met.
