# Cooling Deep Dive

Status: **Air-cooling architecture selected / exact cooler reopened**

## Current decision

The workstation will continue to use **air cooling** for the Ryzen 9 9950X3D, operated at stock/conservative settings.

The previous exact selection of the **Noctua NH-D15 G2 standard** is reopened. It remains an excellent technical reference, but it is no longer allowed to force RAM height, case size or unnecessary cooling spend.

The next cooler pass should compare at least:

1. **Thermalright Phantom Spirit 120-class** — value baseline;
2. **Noctua NH-U12A** — compact premium/serviceability option;
3. **Noctua NH-D15 G2 standard** — maximum-air-cooling reference.

Other air coolers may be considered if they materially improve the same workload/value criteria.

## Architecture that remains selected

Air cooling is still preferred because the build prioritizes stability, serviceability and long ownership over maximum benchmark thermal capacity.

Advantages relevant to this workstation:

- no pump as an additional wear/failure item;
- no coolant, tubing or seals;
- heatsink body has essentially no active wear mechanism;
- standard fans are independently replaceable;
- simpler troubleshooting and maintenance;
- no radiator-placement dependency;
- sufficient cooling is available for stock/conservative 9950X3D operation.

Liquid cooling is not prohibited, but it should be reconsidered only if real measurements show that a suitable air cooler cannot meet the desired sustained thermal/acoustic target.

## Why the exact cooler was reopened

The original NH-D15 G2 choice was made when the build carried substantially more speculative headroom:

- a very large North XL chassis;
- a future extremely high-power GPU assumption;
- a stronger bias toward maximum thermal margin;
- temporary/then-256-GB RAM assumptions that have since been removed.

The build has now been deliberately simplified. The CPU will remain stock/conservative, the final memory configuration is 2×64 GB, and the case itself is being value-checked.

The cooler should therefore be selected for the **actual sustained workload**, not for the highest cooling capacity available.

## Workload requirement

The exact cooler must:

- sustain long Java/Gradle/Maven/test workloads on the 9950X3D without material thermal throttling;
- remain acceptably quiet during typical development work;
- tolerate synthetic worst-case testing as a validation check, not as the design workload;
- operate reliably with normal case airflow;
- fit cleanly with the exact 2×64 GB memory kit and final chassis.

The objective is not the lowest possible benchmark temperature. The objective is **stable sustained operation with sensible acoustics and adequate thermal margin**.

## Evaluation priority

Rank candidates in this order:

1. **sufficient sustained cooling at stock/conservative CPU settings**;
2. **acoustics under representative sustained workload**;
3. **clean RAM/case/motherboard compatibility**;
4. **reliability and serviceability**;
5. **fan/mounting ecosystem and warranty**;
6. **purchase price and replacement-fan cost**;
7. extra thermal capacity only when it provides a real acoustic/reliability benefit.

Do not reward maximum heat-removal capacity merely because it exists.

## Candidate roles

### Thermalright Phantom Spirit 120-class

Role: **value baseline**.

Why it matters:

- compact relative to giant dual-140 mm towers;
- substantially lower purchase price than premium Noctua options;
- strong modern air-cooling performance;
- likely easier fit in a normal ATX case.

Questions for the final pass:

- exact variant/SKU and Romanian availability;
- measured 9950X3D-class thermal/noise behavior;
- RAM clearance with the final 2×64 GB kit;
- fan quality and long-term replacement path;
- warranty/support quality.

### Noctua NH-U12A

Role: **premium compact reference**.

Why it matters:

- smaller height/footprint than NH-D15 G2;
- strong RAM compatibility;
- premium replaceable fans;
- mature SecuFirm mounting/support ecosystem;
- six-year-class warranty/support tradition;
- likely easier fit in a regular mid-tower chassis.

It should win only if the Noctua support/acoustic/serviceability premium is worth the additional cost over the best value candidate.

### Noctua NH-D15 G2 standard

Role: **maximum-air-cooling reference**, no longer the incumbent purchase.

Strengths remain:

- flagship air-cooling capacity;
- excellent noise-normalized behavior;
- premium fans;
- mature mounting/support ecosystem;
- AM5 offset mounting;
- strong warranty/serviceability.

But its size and RAM/front-fan clearance are now explicit costs. It should be selected only if its extra thermal/acoustic margin is materially useful for this stock/conservative workstation.

## RAM and case interaction

The final memory configuration is **2×64 GB / 1DPC**. Exact DIMM height is still open.

The cooler decision must not artificially constrain the RAM search to unusually short DIMMs unless there is a clear benefit. Likewise, the chassis should not be enlarged solely to make room for a cooler whose extra capacity is unnecessary.

Therefore cooler + RAM + case compatibility is evaluated as a coupled physical-fit problem:

- cooler total height including any fan lift;
- DIMM height;
- front-fan interference;
- motherboard VRM/I/O heatsink clearance;
- first PCIe-slot/GPU clearance;
- case side-panel clearance.

## Fan-control strategy

Regardless of final cooler:

- keep CPU stock/conservative;
- use a smooth PWM curve rather than chasing short Ryzen temperature spikes;
- tune against sustained development workloads;
- validate with a separate synthetic thermal test;
- do not enable extra CPU power merely because unused thermal headroom exists.

## Bring-up validation

After assembly:

1. verify all CPU fans report RPM and PWM control;
2. run a sustained representative Java/test/build workload;
3. run a synthetic CPU thermal test separately;
4. log package/CCD temperatures, clocks and fan RPM;
5. confirm no material thermal throttling under the selected stock/conservative policy;
6. tune the fan curve for acceptable sustained noise;
7. repeat with the case closed and combined CPU/GPU activity.

## Long-term maintenance

For any selected air cooler:

- clean fins during normal dust maintenance;
- inspect fan bearings/noise periodically;
- replace individual fans when they degrade;
- repaste when the cooler is removed or sustained temperatures materially drift;
- retain mounting hardware/documentation.

## Current conclusion

> **High-quality air cooling remains selected. Exact cooler model is open.**

The NH-D15 G2 is no longer a closed purchase. The next optimization should choose the least expensive/least bulky air cooler that meets the real 9950X3D thermal, acoustic, compatibility and long-service requirements, with premium Noctua options justified only by durable benefits rather than maximum benchmark capacity.
