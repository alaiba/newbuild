# Memory Deep Dive

Status: **Phase-1 memory selected / 256 GB endpoint deferred**

## Fixed strategy

The memory strategy has two deliberately independent levels:

- **Architectural endpoint:** preserve a credible path to **256 GB** system memory.
- **Phase-1 minimum:** **32 GB** in a simple, stable configuration that reliably boots and runs the workstation.

Phase-1 RAM is explicitly **temporary commissioning memory**. It does not need to resemble the eventual 256 GB configuration, use ECC, maximize frequency, or preserve an upgrade path through the same DIMMs.

The Phase-1 memory should be treated as **replaceable**, not as a sunk-cost constraint on the eventual 256 GB configuration. Reuse or resale later is a bonus, not a design requirement.

## Selected Phase-1 memory — 2026-08-31

**GOODRAM 32 GB DDR5-5600 CL46 — `GR5600D564L46/32G` — 1×32 GB**

This replaces the previously provisional Kingston FURY Beast `KF560C30BBEK2-32` 2×16 GB kit.

### Why this is the better Phase-1 purchase

The current Romanian DDR5 market remains unusually expensive. At the 2026-08-31 purchase-readiness pass:

- PC Garage: GOODRAM `GR5600D564L46/32G` approximately **2,199.99 lei**, in stock;
- PC Garage: Kingston FURY Beast `KF560C30BBEK2-32` approximately **2,998.99 lei**;
- broader Romanian GOODRAM offers begin around **2.08–2.15k lei**.

The GOODRAM therefore saves roughly **800 lei** versus the Kingston kit at the preferred retailer while still satisfying the only hard Phase-1 requirement: 32 GB of stable DDR5 memory.

That saving is material because the Phase-1 RAM is intentionally disposable. Paying roughly 36% more for dual-channel bandwidth, tighter timings and an EXPO profile that are not part of the long-term configuration is poor use of the build budget.

### Why one DIMM is acceptable

A 1×32 GB configuration gives up dual-channel aggregate bandwidth relative to 2×16 GB. This can reduce performance in memory-bandwidth-sensitive workloads and is **not** the desired long-term configuration.

It is nevertheless appropriate for Phase 1 because:

- the goal is reliable commissioning and basic productive use, not peak benchmark performance;
- one DIMM is the simplest memory-controller load and therefore an easy stability target;
- capacity remains 32 GB, matching the commissioning floor;
- the module operates at standard **DDR5-5600 CL46, 1.1 V** rather than depending on an overclocking profile;
- AMD officially specifies DDR5-5600 support for the Ryzen 9 9950X3D with both 2×1R and 2×2R configurations, so 5600 MT/s is within the CPU's normal two-DIMM memory class rather than an EXPO target;
- the module will be replaced rather than expanded when the final 256 GB configuration is purchased.

If Phase 1 lasts unexpectedly long and single-channel bandwidth becomes a measurable productivity problem, do **not** automatically buy a second unmatched module. Reassess whether it is then better to accelerate the final 256 GB purchase.

## Selected module characteristics

Manufacturer data for `GR5600D564L46/32G`:

- 32 GB;
- 1×32 GB;
- DDR5 UDIMM, 288-pin desktop memory;
- DDR5-5600;
- CL46;
- 1.1 V;
- 2048×8 organization;
- no heatsink / no RGB;
- approximately **133.35 × 31.25 × 3.6 mm**;
- lifetime manufacturer warranty.

The 31.25 mm module height is also useful mechanically: it fits under the NH-D15 G2's approximately 32 mm normal dual-fan RAM clearance, so the selected Phase-1 configuration requires **no front-fan lift**.

Manufacturer reference:
- https://www.goodram.com/produkty/goodram-ddr5-dimm/

CPU memory reference:
- https://www.amd.com/en/products/processors/desktops/ryzen/9000-series/amd-ryzen-9-9950x3d.html

## QVL / compatibility posture

The exact GOODRAM SKU was not found as an explicitly validated ProArt QVL entry during this purchase pass. That is acceptable for this deliberately simple commissioning configuration because:

- motherboard QVLs are not exhaustive support lists;
- this is an ordinary JEDEC-class 1.1 V DDR5 UDIMM rather than an aggressive EXPO/XMP configuration;
- only one DIMM is populated initially, minimizing electrical/training complexity;
- the module is temporary and can be exchanged if the individual board/module combination shows an unexpected training problem.

The more expensive Kingston `KF560C30BBEK2-32` remains a known-compatible fallback, but its roughly 800 lei premium is not justified merely to obtain a QVL/configurator match for throw-away Phase-1 RAM.

## Installation / operating policy

For commissioning:

1. install the single 32 GB DIMM in the motherboard's recommended slot for a one-DIMM configuration (normally **A2**; confirm against the current ProArt manual before assembly);
2. update the ProArt BIOS before serious testing;
3. boot at **Auto/JEDEC** settings;
4. do not manually overclock the Phase-1 DIMM;
5. accept an automatically selected lower data rate if firmware chooses one for stability;
6. run an extended memory test before treating the system as commissioned;
7. record the installed DIMM part number and actual negotiated speed/timings.

There is no reason to tune this temporary module for latency or bandwidth.

## Retailer policy

Procurement preference remains:

1. **PC Garage** first;
2. **eMAG** second;
3. another reputable Romanian/EU retailer only when the preferred sources are materially worse on price/availability.

At approximately 2,199.99 lei, PC Garage is close enough to the broader Romanian market for the preferred-retailer rule to win.

Reopen the exact Phase-1 SKU only if:

- PC Garage stock disappears before ordering;
- its price rises materially relative to another ordinary 32 GB DDR5 UDIMM;
- an exact compatibility/training problem appears;
- or a substantially better-value 32 GB+ commissioning option becomes available.

## ECC posture

**System-level ECC remains a strong preference for the eventual long-term memory configuration, but it is not a requirement for Phase 1.**

The rationale is reliability rather than performance. A long-lived workstation with large JVM heaps, multiple VMs/containers, databases and long-running build/test/analysis workloads has meaningful memory-resident state worth protecting. ECC can reduce the risk that a memory fault becomes a silent data corruption, unexplained process/test failure, VM crash or corrupted in-memory/page-cache state.

DDR5 on-die ECC is not equivalent to system-level ECC: on-die ECC only corrects errors internal to individual DRAM devices and does not provide the same end-to-end protection across the module/bus/controller path.

For the eventual high-capacity configuration, prefer ECC UDIMM if all of the following are true:

- the selected motherboard officially supports ECC UDIMM with the 9950X3D;
- the target capacity is credibly supported/validated;
- correctable and uncorrectable ECC events are exposed to Windows/Linux in a way that can actually be monitored;
- stable operation does not require marginal tuning;
- the cost and data-rate trade-off are reasonable relative to the reliability benefit.

Do not select ECC merely because a board can boot ECC DIMMs. If ECC reporting is hidden/non-functional, capacity support is weak, or the available configuration is materially less stable than a proven non-ECC configuration, prefer the more reliable overall system rather than the ECC label.

## Eventual 256 GB configuration

The endpoint remains **4×64 GB or equivalent**.

At upgrade time:

1. reassess the ProArt's current BIOS/AGESA and QVL;
2. identify the best exact 4×64 GB configuration then available;
3. prefer ECC UDIMM if exact 64 GB modules, four-DIMM support, stability and OS-visible reporting are all credible;
4. otherwise choose a strongly validated 4×64 GB non-ECC configuration;
5. start at JEDEC/Auto and accept 5200 MT/s or lower if required for stability;
6. avoid EXPO/XMP merely to preserve headline frequency at 256 GB;
7. perform extended memory stability testing;
8. if ECC is used, verify Windows WHEA and/or Linux EDAC/RAS reporting before treating ECC as operationally useful.

**RDIMM is incompatible with this AM5 platform.** Many 64 GB server ECC products are RDIMMs and must not be confused with ECC UDIMMs.

## Workload implications

The selected 1×32 GB Phase-1 configuration deliberately sacrifices some memory bandwidth. The main practical constraints are:

- less bandwidth than a dual-DIMM configuration;
- only the same capacity as the current commissioning floor;
- limited concurrency headroom for combinations of IntelliJ, Android Studio, emulators, Docker/WSL2, local services and VMs.

Those costs are accepted because this is a temporary configuration purchased specifically to release budget for permanent components.

The 256 GB endpoint remains valuable for larger JVM heaps, more concurrent JVMs/IDEs/services/VMs, local databases/data processing and future AI support workflows.

## Selected conclusion

- **Phase-1 exact memory:** GOODRAM 32 GB DDR5-5600 CL46 `GR5600D564L46/32G`, **1×32 GB — Selected**.
- **Phase-1 objective:** stable commissioning and usable 32 GB capacity at minimum sensible sunk cost.
- **Dual-channel:** deliberately deferred; not worth ~800 lei extra for temporary RAM at current pricing.
- **EXPO/XMP:** unnecessary for Phase 1.
- **Long-term endpoint:** 256 GB, expected 4×64 GB; exact modules and ECC verdict deferred.
- **Upgrade policy:** replace the Phase-1 DIMM rather than designing the final configuration around it.
