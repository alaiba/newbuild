# Memory Deep Dive

Status: **Under review / Phase-1 commissioning memory + 256 GB endpoint**

## Fixed strategy

The memory strategy has two deliberately independent levels:

- **Architectural endpoint:** preserve a credible path to **256 GB** system memory.
- **Phase-1 minimum:** **32 GB** in any simple, stable configuration that reliably boots and runs the workstation.

Phase-1 RAM is explicitly **temporary commissioning memory**. It does not need to resemble the eventual 256 GB configuration, use ECC, maximize frequency, or preserve an upgrade path through the same DIMMs.

If buying new, **2×16 GB** is preferred when it costs about the same as alternatives because it preserves dual-channel bandwidth. However, **1×32 GB or any other stable 32 GB-or-larger configuration is acceptable** if it is materially cheaper or more convenient.

This lets memory act as the build's strongest budget-release valve without weakening the CPU/platform, motherboard, chassis, cooling, storage or PSU architecture.

The Phase-1 kit should be treated as **replaceable**, not as a sunk-cost constraint on the eventual 256 GB configuration. Reuse or resale later is a bonus, not a design requirement.

## ECC posture

**System-level ECC is a strong preference for the eventual long-term memory configuration, but not a requirement for Phase 1.**

The rationale is reliability rather than performance. A long-lived workstation with large JVM heaps, multiple VMs/containers, databases and long-running build/test/analysis workloads has meaningful memory-resident state worth protecting. ECC can reduce the risk that a memory fault becomes a silent data corruption, unexplained process/test failure, VM crash or corrupted in-memory/page-cache state.

The Ryzen 9 9950X3D supports ECC when the motherboard implements it. DDR5 on-die ECC is not equivalent to system-level ECC: on-die ECC only corrects errors internal to individual DRAM devices and does not provide the same end-to-end protection across the module/bus/controller path.

For the eventual high-capacity configuration, prefer ECC UDIMM if all of the following are true:

- the selected motherboard officially supports ECC UDIMM with the 9950X3D;
- the target capacity is credibly supported/validated;
- correctable and uncorrectable ECC events are exposed to Windows/Linux in a way that can actually be monitored;
- stable operation does not require marginal tuning;
- the cost and data-rate trade-off are reasonable relative to the reliability benefit.

Do not select ECC merely because a board can boot ECC DIMMs. If ECC reporting is hidden/non-functional, capacity support is weak, or the available configuration is materially less stable than a proven non-ECC configuration, prefer the more reliable overall system rather than the ECC label.

For **Phase 1**, do not pay a material premium for ECC. The temporary kit's job is simply to commission and use the system reliably until the long-term 256 GB purchase makes sense.

## Review focus

The review now has two outputs to optimize separately.

### Phase-1 commissioning memory

Determine the lowest-cost stable current option at **32 GB or more**:

- 32 GB as **2×16 GB** — preferred when similarly priced because it preserves dual-channel bandwidth;
- 32 GB as **1×32 GB** — acceptable when it is cheaper or easier to source;
- 48/64/96/128 GB — acceptable only when the incremental price is attractive enough to justify more temporary capacity;
- ordinary JEDEC or conservative EXPO/XMP operation;
- non-ECC is fully acceptable;
- Romanian/EU availability and price.

Do not optimize temporary RAM for eventual reuse. Do not let heat-spreader height, RGB, extreme timings or overclocking profiles complicate cooling or stability.

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

A 32 GB Phase-1 configuration is acceptable because that capacity is already sufficient for the current working environment. The new system can therefore deliver most of its CPU/platform responsiveness immediately without requiring an expensive memory purchase merely to commission the build.

The main limitation of remaining at 32 GB is concurrency headroom: heavier combinations of IntelliJ, Android Studio, emulators, Docker/WSL2, local services and VMs may create memory pressure sooner. That is acceptable in Phase 1 because the kit is intentionally temporary.

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

Do **not** assume the Phase-1 kit will be expanded into the final 256 GB configuration.

When the move to 256 GB becomes economically justified:

1. reassess the motherboard's current BIOS/AGESA and QVL state;
2. select the best validated 4×64 GB (or equivalent) configuration available at that time;
3. prefer a single matched kit/configuration where possible;
4. replace/resell/reuse the Phase-1 kit if convenient rather than compromising stability to preserve sunk cost.

## Dependencies

The Phase-1 kit only requires ordinary compatibility with the provisional motherboard and stable operation at 32 GB or more.

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

1. exact **Phase-1** recommendation at 32 GB or more, optimized for lowest reasonable cost and stability;
2. current price/value comparison only where a larger temporary configuration is compelling;
3. exact **eventual 256 GB** capacity/topology recommendation;
4. exact 256 GB kit/model recommendation or shortlist when economically relevant;
5. QVL/platform support evidence;
6. JEDEC and EXPO/XMP characteristics;
7. expected stable operating settings;
8. **ECC/non-ECC verdict based on real implementation, observability, stability and cost** for the long-term configuration;
9. stability-test procedure, including ECC-event validation where applicable; and
10. Romanian/EU availability and price.
