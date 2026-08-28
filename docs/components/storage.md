# Storage Deep Dive

Status: **Open**

## Scope

No storage capacity, drive count, interface generation, NAND class or exact model has been selected.

The previously discussed **2 TB system SSD + 4 TB work/VM SSD** arrangement is a candidate architecture only.

## Review focus

Determine from the workload:

- required initial and future capacity
- one drive versus multiple physical drives
- whether OS/workload/VM/container separation provides a real operational or performance benefit
- TLC, QLC and other NAND trade-offs
- DRAM versus DRAM-less controller designs
- sustained write behavior after SLC cache exhaustion
- endurance / TBW
- latency and random-I/O behavior relevant to VMs/build trees/containers
- firmware maturity and update tooling
- thermals and throttling
- PCIe 4.0 versus PCIe 5.0 value
- motherboard lane/slot topology
- double-sided drive fit where applicable
- backup/recovery implications
- Romanian pricing/value

## Required output

Finish with:

1. justified storage capacity
2. justified drive count/topology
3. exact drive recommendation(s)
4. preferred slot assignment after motherboard selection
5. endurance and sustained-I/O rationale
6. firmware/thermal requirements
7. backup/recovery implications
8. alternative models if pricing changes materially
