# Memory Deep Dive

Status: **Under review / 256 GB target**

## Fixed target

The build should target **256 GB of installed system memory initially**.

This is no longer an open capacity-comparison exercise. The default objective is to identify the best stable 256 GB configuration for the selected Ryzen 9 9950X3D + AM5 platform.

Scale back to 192 GB or 128 GB only if:

- current Romanian/EU pricing makes 256 GB disproportionate to its benefit; or
- the available 256 GB configurations require an unacceptable stability/performance compromise on AM5.

The exact DIMM topology, kit, operating data rate, timings and ECC/non-ECC mode remain open.

## ECC posture

**System-level ECC is a strong preference for this workstation, but not yet a hard requirement.**

The rationale is reliability rather than performance. A 256 GB workstation with long uptimes, large JVM heaps, multiple VMs/containers, databases and long-running build/test/analysis workloads has more memory state worth protecting than a typical desktop. ECC can reduce the risk that a memory fault becomes a silent data corruption, unexplained process/test failure, VM crash or corrupted in-memory/page-cache state.

The Ryzen 9 9950X3D supports ECC when the motherboard implements it. DDR5 on-die ECC is not equivalent to system-level ECC: on-die ECC only corrects errors internal to individual DRAM devices and does not provide the same end-to-end protection across the module/bus/controller path.

Prefer a 256 GB ECC UDIMM configuration if all of the following are true:

- the selected motherboard officially supports ECC UDIMM with the 9950X3D;
- 4×64 GB ECC UDIMMs are available and credibly supported/validated;
- correctable and uncorrectable ECC events are exposed to Windows/Linux in a way that can actually be monitored;
- stable operation does not require marginal tuning;
- the cost and data-rate trade-off are reasonable relative to the reliability benefit.

Do not select ECC merely because a board can boot ECC DIMMs. If ECC reporting is hidden/non-functional, 256 GB support is weak, or the available configuration is materially less stable than a proven non-ECC configuration, prefer the more reliable overall system rather than the ECC label.

## Review focus

Determine the best practical 256 GB implementation for the expected 10-year-oriented lifetime:

- exact 256 GB topology, expected to require 4×64 GB unless a supported alternative exists
- motherboard and CPU memory-controller limits
- realistic stable data rate at 256 GB
- JEDEC versus EXPO/XMP trade-offs
- ECC versus non-ECC value and implementation quality
- exact 256 GB ECC UDIMM availability and QVL/support evidence
- motherboard QVL/support evidence for 64 GB DIMMs and four-DIMM operation
- high-density DIMM firmware/AGESA maturity
- memory-training and boot-time implications
- effect of four-DIMM operation on latency/bandwidth and development workloads
- safe/conservative voltage requirements
- long-duration thermal behavior of four high-density DIMMs
- upgrade/serviceability implications of starting at the platform maximum
- Romanian/EU availability and price

Stability is more important than headline memory frequency. Avoid configurations that rely on marginal memory-controller overclocking, unusually aggressive SoC/memory voltages or fragile training behavior merely to preserve a marketing data rate.

## Workload implications

ECC is not expected to make Java compilation, Gradle/Maven, IntelliJ, Android Studio, containers or local databases faster. Its value is the reduced probability of rare memory faults becoming corrupted state or difficult-to-reproduce failures.

The case for ECC is stronger here because:

- the target capacity is 256 GB rather than a typical 32–64 GB desktop configuration;
- the machine is intended for long professional sessions and potentially long-running services/VMs;
- build/test/database workloads can retain or transform large amounts of memory-resident state;
- the system is expected to remain in service for roughly a decade;
- future local-AI workloads may involve long-running preprocessing, training or inference tasks where repeatability and data integrity matter.

System RAM ECC is separate from GPU-memory ECC. A future professional AI GPU may provide ECC VRAM independently; selecting ECC system memory does not change GPU VRAM protection, and non-ECC system memory does not prevent using an ECC-capable GPU.

## Fallback analysis

Do not treat 128 GB, 192 GB and 256 GB as equal candidates. The review should first solve for 256 GB, then quantify the fallback options only if needed.

If 256 GB is problematic, document:

1. exact 256 GB total memory cost versus 192 GB and 128 GB
2. stable operating speed/timings at each capacity
3. whether the 256 GB limitation is board-specific, kit-specific or inherent to the CPU memory controller/topology
4. whether another eligible motherboard materially improves 256 GB behavior
5. the real workload consequence of scaling back capacity
6. the cost or stability threshold that justifies reducing capacity
7. whether ECC is the limiting factor and whether a non-ECC 256 GB configuration is materially more mature/stable

## Dependencies

An exact kit should not be selected until the motherboard shortlist is sufficiently mature to evaluate:

- official 256 GB support
- 64 GB DIMM/QVL evidence
- realistic 4×64 GB operating data rate
- ECC implementation
- availability of 64 GB ECC UDIMMs and a complete 256 GB ECC configuration
- BIOS/firmware maturity
- memory-training behavior
- OS-visible ECC event reporting where applicable

## Required output

The memory review must finish with:

1. exact 256 GB capacity/topology recommendation
2. exact kit/model recommendation or shortlist
3. QVL/platform support evidence
4. JEDEC and EXPO/XMP characteristics
5. expected stable operating settings
6. **ECC/non-ECC verdict based on real implementation, observability, stability and cost**
7. expected performance impact versus lower-capacity/faster configurations
8. stability-test procedure, including ECC-event validation where applicable
9. Romanian/EU availability and price
10. fallback recommendation only if 256 GB is economically or technically disproportionate
