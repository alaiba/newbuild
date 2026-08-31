# RAM Capacity Sensitivity — 2026-08-31

> **Resolved analysis. Final decision: 48 GB / 2×24 GB.**
>
> This document records the analysis that reopened the original 128 GB plan. The later decision selected **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24 GB), DDR5-5600, 1DPC**. Any earlier recommendation below for 64 or 128 GB is superseded by that final decision.

## Final decision

Selected:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2×24 GB DDR5-5600, non-ECC, A2/B2 / 1DPC.**

Why 48 GB won:

- capacity below 128 GB does not intrinsically slow the Ryzen 9 9950X3D while the working set fits and the system remains a two-DIMM configuration;
- 48 GB preserves the desired two-DIMM / 1DPC topology and DDR5-5600 class;
- current 48 GB pricing is dramatically better than 64/128 GB pricing;
- 32 GB is too close to the current machine's constraint and poor value versus 48 GB;
- 96 GB is priced too close to 128 GB;
- the extra cost of 64 GB was not justified by the additional 16 GB of concurrency headroom at current prices.

If 48 GB later proves insufficient under measured real workloads, **replace the pair with a larger matched two-DIMM kit**. Do not add another pair merely to preserve the initial purchase.

## Core performance conclusion

Capacity below 128 GB does not intrinsically slow the CPU as long as memory remains a two-DIMM DDR5-5600 configuration and the active working set fits in RAM.

The performance loss from buying less RAM is therefore mostly **threshold-based rather than proportional**:

- below the capacity threshold: usually negligible capacity-related performance loss;
- near the threshold: reduced filesystem cache and more aggressive memory reclamation can make the system less responsive;
- beyond the threshold: paging, compressed memory, JVM/IDE GC pressure, VM/container limits and forced workload serialization can cause large wall-clock slowdowns.

By contrast, populating four DIMMs is a deterministic topology compromise. AMD specifies a lower supported memory rate for four populated DIMMs than for two, so the project deliberately avoids a planned four-DIMM upgrade path.

## Meaningful capacities considered

| Capacity | Topology | Raw memory-speed effect vs 128 GB 2×64 while workload fits | Final interpretation |
|---|---|---|---|
| 32 GB | 2×16 GB | ~0% | Rejected: too restrictive and poor value versus 48 GB |
| **48 GB** | **2×24 GB** | **~0%** | **Selected: best current utility per leu** |
| 64 GB | 2×32 GB | ~0% | Rejected at current price: good technically, insufficient value over 48 GB |
| 96 GB | 2×48 GB | ~0% | Rejected: priced too close to 128 GB |
| 128 GB | 2×64 GB | baseline | Rejected at current price: maximum headroom but disproportionate cost |

Single-DIMM configurations are rejected because they give up normal dual-channel operation. Four-DIMM configurations are rejected as planned endpoints because they move the platform away from the preferred 1DPC topology.

## Practical capacity envelope

Installed RAM is not the same as application working-set budget. Windows, drivers, security software, filesystem cache, background services and native allocations consume memory too.

A practical planning envelope used during the analysis was:

| Installed | Comfortable active application / VM / container working set before pressure becomes likely |
|---:|---:|
| 32 GB | ~22–26 GB |
| **48 GB** | **~35–40 GB** |
| 64 GB | ~48–55 GB |
| 96 GB | ~75–82 GB |
| 128 GB | ~100–110 GB |

These are planning ranges, not hard limits. Real usage must be measured after commissioning.

## Workload interpretation for 48 GB

48 GB should be adequate for normal heavy Java development with meaningful WSL/container concurrency, but it can approach pressure under combinations such as:

- very large IntelliJ/Android Studio projects;
- Gradle/Maven/Kotlin daemons and build JVMs;
- Android emulator(s);
- WSL2 / Docker / local services;
- local databases;
- a heavy browser/desktop session.

The selected strategy is therefore to **measure committed memory during real work** rather than pre-buy expensive headroom.

## Performance-loss model

| State | Estimated effect versus a larger configuration |
|---|---|
| Working set comfortably fits | **~0–2%** capacity-related difference for CPU/build work; often effectively zero |
| Fits, but little RAM left for filesystem cache | often **~0–5%** on I/O-sensitive repeated workflows; workload-dependent |
| Moderate memory pressure / occasional paging | **~5–20%** wall-clock degradation plausible, plus visible latency spikes |
| Sustained paging / compressed-memory pressure | **20–50%+** slowdown plausible; interactivity can degrade more than averages suggest |
| Workload cannot fit at all | workload must be reduced, serialized or memory capacity increased |

The pressure ranges are engineering estimates, not benchmark claims for the exact source tree.

## Upgrade rule

If telemetry later shows persistent memory pressure:

1. confirm that RAM, rather than CPU/storage, is the actual bottleneck;
2. choose a larger matched **two-DIMM** kit available at that time;
3. replace the 2×24 GB pair;
4. resell or repurpose the original kit;
5. do not add a second pair merely because two slots remain free.

## Procurement reference

At the time of the decision, the selected 48 GB Crucial Pro kit surfaced in Romania around the ~2.9k-leu class, materially below the 64/128 GB alternatives. Supplier and delivered price remain checkout-time variables.

The exact selected SKU is **`CP2K24G56C46U5`**. Do not substitute a single 48 GB DIMM such as `CP24G56C46U5`.
