# Decision Log

This file records decisions that have been closed, together with the reason and any conditions that could reopen them.

## Decision status vocabulary

- **Proposed** — current working direction, not yet deeply reviewed
- **Under review** — active technical evaluation
- **Selected** — decision closed unless a dependency changes
- **Rejected** — explicitly considered and not selected
- **Deferred** — intentionally postponed

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| GPU | Reuse NVIDIA GeForce RTX 3060 12 GB initially | Selected | Adequate for current gaming and useful for entry-level CUDA/local AI; upgrade only when a materially higher-VRAM GPU is justified |
| Memory topology | Target 128 GB as 2×64 GB rather than 4×32 GB | Proposed | Lower DIMM count should improve memory-controller margin and future expansion flexibility; exact kit depends on motherboard |
| CPU cooling philosophy | Prefer high-end air cooling over AIO | Proposed | Fewer long-term failure modes; reopen only if sustained 9950X workload performance is materially constrained |
| CPU | AMD Ryzen 9 9950X | Proposed | Strong fit for development/VM/container workload; detailed review still pending |
| Motherboard | MSI MAG X870 TOMAHAWK WIFI | Under review | Must pass memory, ECC, PCIe/M.2 topology, I/O, reliability and longevity review |
| Storage topology | Separate 2 TB system and 4 TB work/VM NVMe drives | Proposed | Separation is useful operationally and isolates high-I/O VM/container workloads |
| PSU class | 1000 W high-quality ATX 3.1 | Proposed | Excessive for RTX 3060 but preserves headroom for future high-power GPU |
