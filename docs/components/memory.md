# Memory Deep Dive

Status: **Under review / 256 GB target**

## Fixed target

The build should target **256 GB of installed system memory initially**.

This is no longer an open capacity-comparison exercise. The default objective is to identify the best stable 256 GB configuration for the selected Ryzen 9 9950X3D + AM5 platform.

Scale back to 192 GB or 128 GB only if:

- current Romanian/EU pricing makes 256 GB disproportionate to the overall build budget; or
- the available 256 GB configurations require an unacceptable stability/performance compromise on AM5.

The exact DIMM topology, kit, operating data rate, timings and ECC/non-ECC mode remain open.

## Review focus

Determine the best practical 256 GB implementation for the expected 7–10 year lifetime:

- exact 256 GB topology, expected to require 4×64 GB unless a supported alternative exists
- motherboard and CPU memory-controller limits
- realistic stable data rate at 256 GB
- JEDEC versus EXPO/XMP trade-offs
- ECC versus non-ECC value and implementation quality
- motherboard QVL/support evidence for 64 GB DIMMs and four-DIMM operation
- high-density DIMM firmware/AGESA maturity
- memory-training and boot-time implications
- effect of four-DIMM operation on latency/bandwidth and development workloads
- upgrade/serviceability implications of starting at the platform maximum
- Romanian/EU availability and price

Stability is more important than headline memory frequency. Avoid configurations that rely on marginal memory-controller overclocking or unusually aggressive manual tuning merely to preserve a marketing data rate.

## Fallback analysis

Do not treat 128 GB, 192 GB and 256 GB as equal candidates. The review should first solve for 256 GB, then quantify the fallback options only if needed.

If 256 GB is problematic, document:

1. exact 256 GB total memory cost versus 192 GB and 128 GB
2. stable operating speed/timings at each capacity
3. whether the 256 GB limitation is board-specific, kit-specific or inherent to the CPU memory controller/topology
4. whether another eligible motherboard materially improves 256 GB behavior
5. the real workload consequence of scaling back capacity
6. the cost or stability threshold that justifies reducing capacity

## Dependencies

An exact kit should not be selected until the motherboard shortlist is sufficiently mature to evaluate:

- official 256 GB support
- 64 GB DIMM/QVL evidence
- realistic 4×64 GB operating data rate
- ECC implementation
- BIOS/firmware maturity
- memory-training behavior

## Required output

The memory review must finish with:

1. exact 256 GB capacity/topology recommendation
2. exact kit/model recommendation or shortlist
3. QVL/platform support evidence
4. JEDEC and EXPO/XMP characteristics
5. expected stable operating settings
6. ECC/non-ECC rationale
7. expected performance impact versus lower-capacity/faster configurations
8. stability-test procedure
9. Romanian/EU availability and price
10. fallback recommendation only if 256 GB is economically or technically disproportionate
