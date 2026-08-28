# Memory Deep Dive

Status: **Open**

## Scope

No memory capacity, DIMM topology, speed, vendor or ECC mode has been selected.

The previously discussed **128 GB as 2×64 GB DDR5-5600** is a useful hypothesis to test, not a target that must be preserved.

## Review focus

Determine from the actual workload and expected 7–10 year lifetime:

- required initial capacity
- realistic future capacity requirement
- whether 64 GB, 96 GB, 128 GB, 192 GB, 256 GB or another capacity is justified
- optimal DIMM count/topology for the selected CPU/platform
- stable supported data rates at that capacity
- JEDEC versus EXPO/XMP trade-offs
- ECC versus non-ECC value and implementation quality
- high-density DIMM support and firmware maturity
- upgradeability versus buying final capacity up front
- memory-training and boot-time implications
- Romanian availability and price

## Dependencies

An exact kit should not be selected until the CPU/platform and motherboard shortlist is sufficiently mature to evaluate:

- memory-controller limits
- motherboard QVL/support evidence
- ECC implementation
- realistic speed at the intended capacity/topology
- BIOS/firmware maturity

## Required output

The memory review must finish with:

1. justified capacity recommendation
2. justified DIMM topology
3. exact kit/model recommendation or shortlist
4. QVL/platform support evidence
5. JEDEC and EXPO/XMP characteristics
6. expected stable operating settings
7. ECC/non-ECC rationale
8. upgrade-path implications
9. stability-test procedure
10. Romanian availability and price
