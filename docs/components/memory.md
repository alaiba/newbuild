# Memory Deep Dive

Status: **Under review / initial purchase + 256 GB endpoint**

## Fixed strategy

The memory strategy has two distinct levels:

- **Architectural endpoint:** preserve a credible path to **256 GB** system memory.
- **Minimum initial purchase:** **64 GB as 2×32 GB**.

The initial kit does not have to reach 256 GB if current high-capacity DDR5 pricing is disproportionate. A larger starting point such as 96 GB (2×48 GB) or 128 GB (2×64 GB) may still be selected if the price/value is sensible, but 64 GB is the accepted floor.

This lets memory act as the build's budget-release valve without weakening the CPU/platform, motherboard, chassis, cooling, storage or PSU architecture.

The initial lower-capacity kit should be treated as **replaceable**, not as a sunk-cost constraint on the eventual 256 GB configuration. Do not assume that buying a second nominally identical kit later is equivalent to a vendor-validated four-DIMM set.

## ECC posture

**System-level ECC is a strong preference for this workstation, but not yet a hard requirement.**

The rationale is reliability rather than performance. A workstation with long uptimes, large JVM heaps, multiple VMs/containers, databases and long-running build/test/analysis workloads has meaningful memory-resident state worth protecting. ECC can reduce the risk that a memory fault becomes a silent data corruption, unexplained process/test failure, VM crash or corrupted in-memory/page-cache state.

The Ryzen 9 9950X3D supports ECC when the motherboard implements it. DDR5 on-die ECC is not equivalent to system-level ECC: on-die ECC only corrects errors internal to individual DRAM devices and does not provide the same end-to-end protection across the module/bus/controller path.

For the eventual high-capacity configuration, prefer ECC UDIMM if all of the following are true:

- the selected motherboard officially supports ECC UDIMM with the 9950X3D;
- the target capacity is credibly supported/validated;
- correctable and uncorrectable ECC events are exposed to Windows/Linux in a way that can actually be monitored;
- stable operation does not require marginal tuning;
- the cost and data-rate trade-off are reasonable relative to the reliability benefit.

Do not select ECC merely because a board can boot ECC DIMMs. If ECC reporting is hidden/non-functional, capacity support is weak, or the available configuration is materially less stable than a proven non-ECC configuration, prefer the more reliable overall system rather than the ECC label.

For the **initial 64–128 GB purchase**, ECC should be evaluated on its own price/availability merits. We should not overpay heavily for a temporary ECC kit if the long-term plan is to replace it with a separately validated 256 GB ECC configuration.

## Review focus

The review now has two outputs to optimize separately.

### Initial purchase

Determine the best current-value two-DIMM starting configuration:

- 64 GB as **2×32 GB** — selected minimum floor;
- 96 GB as **2×48 GB** — candidate if price premium is modest;
- 128 GB as **2×64 GB** — candidate if price/value becomes attractive;
- JEDEC versus EXPO/XMP characteristics;
- ECC versus non-ECC price and implementation;
- conservative stable settings;
- Romanian/EU availability and price.

Prefer two DIMMs for the initial configuration to reduce memory-controller loading and preserve a simple, conservative operating point.

### Eventual 256 GB configuration

Determine the best practical 256 GB implementation for the expected 10-year-oriented lifetime:

- exact topology, expected to require 4×64 GB unless a supported alternative exists;
- motherboard and CPU memory-controller limits;
- realistic stable data rate at 256 GB;
- JEDEC versus EXPO/XMP trade-offs;
- ECC versus non-ECC value and implementation quality;
- exact 256 GB ECC UDIMM availability and QVL/support evidence;
- motherboard QVL/support evidence for 64 GB DIMMs and four-DIMM operation;
- high-density DIMM firmware/AGESA maturity;
- memory-training and boot-time implications;
- effect of four-DIMM operation on latency/bandwidth and development workloads;
- safe/conservative voltage requirements;
- long-duration thermal behavior of four high-density DIMMs;
- Romanian/EU availability and price.

Stability is more important than headline memory frequency. Avoid configurations that rely on marginal memory-controller overclocking, unusually aggressive SoC/memory voltages or fragile training behavior merely to preserve a marketing data rate.

## Workload implications

A 64 GB starting configuration is legitimate for this build because it already doubles the user's current working capacity while preserving every other architectural decision. It is sufficient to make serious use of IntelliJ, Android Studio, builds, Docker/WSL2, Android emulators and ordinary local services, though heavier concurrent VM/container/JVM use will benefit from later capacity increases.

The 256 GB endpoint remains valuable for:

- larger JVM heaps and more concurrent JVMs;
- multiple IDEs and Android tooling;
- more aggressive Docker/WSL2/VM concurrency;
- local databases and data processing;
- future AI preprocessing/offload workflows;
- reducing the chance that memory capacity becomes the workstation's limiting resource later in its life.

ECC is not expected to make Java compilation, Gradle/Maven, IntelliJ, Android Studio, containers or local databases faster. Its value is the reduced probability of rare memory faults becoming corrupted state or difficult-to-reproduce failures.

System RAM ECC is separate from GPU-memory ECC. A future professional AI GPU may provide ECC VRAM independently; selecting ECC system memory does not change GPU VRAM protection, and non-ECC system memory does not prevent using an ECC-capable GPU.

## Upgrade policy

Do **not** assume the initial two-DIMM kit will be expanded by adding a second independently purchased kit later.

When the move to 256 GB becomes economically justified:

1. reassess the motherboard's current BIOS/AGESA and QVL state;
2. select the best validated 4×64 GB (or equivalent) configuration available at that time;
3. prefer a single matched kit/configuration where possible;
4. replace/resell the initial kit if necessary rather than compromising stability to preserve sunk cost.

## Dependencies

The initial 64–128 GB kit can be selected once the motherboard shortlist is sufficiently mature to evaluate ordinary two-DIMM compatibility.

The eventual 256 GB configuration still requires:

- official 256 GB motherboard support;
- 64 GB DIMM/QVL evidence;
- realistic 4×64 GB operating data rate;
- ECC implementation;
- availability of 64 GB ECC UDIMMs and a complete 256 GB ECC configuration;
- BIOS/firmware maturity;
- memory-training behavior;
- OS-visible ECC event reporting where applicable.

## Required output

The memory review must finish with:

1. exact **initial** memory recommendation, at least 64 GB as 2×32 GB;
2. current price/value comparison for 64 GB, 96 GB and 128 GB two-DIMM options;
3. ECC/non-ECC recommendation for the initial kit;
4. exact **eventual 256 GB** capacity/topology recommendation;
5. exact 256 GB kit/model recommendation or shortlist when economically relevant;
6. QVL/platform support evidence;
7. JEDEC and EXPO/XMP characteristics;
8. expected stable operating settings;
9. **ECC/non-ECC verdict based on real implementation, observability, stability and cost**;
10. stability-test procedure, including ECC-event validation where applicable; and
11. Romanian/EU availability and price.
