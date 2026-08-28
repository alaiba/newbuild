# Build Requirements

## Workload priority

### Primary

- Programming and general software development
- Docker workloads
- WSL2
- Multiple virtual machines

### Secondary

- Occasional Genshin Impact
- Entry-level local AI experimentation in the future

## Longevity target

The system should remain useful and serviceable for approximately **7–10 years**. Component selection should therefore prioritize:

- platform stability
- maintainability
- replaceability of failure-prone parts
- useful I/O and expansion headroom
- memory capacity and stability
- storage endurance
- good thermal behavior under sustained workloads
- avoiding expenditure on features that are likely to become irrelevant before they provide value

## Budget

- Maximum total project budget: **20,000 lei**
- Location: **Iași, Romania**
- Self-assembled
- Existing NVIDIA GeForce RTX 3060 12 GB will be reused initially

The budget is a ceiling, not a spending target. Money should remain unspent when a more expensive component does not deliver a material benefit for the stated workload or longevity goals.

## Reliability principles

- Prefer **2×64 GB** over 4×32 GB for a 128 GB memory configuration.
- Start with conservative memory settings; enable EXPO only after establishing baseline stability.
- Prefer a high-quality air cooler over an AIO unless liquid cooling provides a compelling workload-specific benefit.
- Avoid manual CPU overclocking.
- Prefer high-endurance TLC NVMe drives for sustained workstation use.
- Keep OS and active VM/Docker storage on separate physical drives where practical.
- Prefer a high-quality ATX 3.1 PSU with a long warranty and enough headroom for a future GPU upgrade.
- Use good chassis airflow and dust filtration.
- Use a UPS.
- Maintain external backups; RAID is not a backup.

## Platform requirements

### CPU/platform

- Strong multi-core performance for development, build, VM and container workloads
- High single-thread performance remains important
- No requirement to optimize primarily for gaming
- Platform should support at least 128 GB RAM comfortably

### Memory

- Target capacity: **128 GB**
- Preferred topology: **2×64 GB**
- Initial target data rate: **DDR5-5600**, subject to board/QVL and stability validation
- Stability is more important than peak memory bandwidth
- ECC should be evaluated explicitly before the motherboard decision is closed

### Storage

At minimum:

1. **System drive:** 2 TB NVMe SSD
2. **Work / VM drive:** 4 TB NVMe SSD

Preferred characteristics:

- PCIe 4.0 is sufficient unless a PCIe 5.0 drive shows a compelling real workload advantage
- TLC NAND preferred
- DRAM cache preferred for heavy workstation usage
- strong write endurance
- proven firmware and thermal behavior

### GPU

- Reuse NVIDIA GeForce RTX 3060 12 GB initially
- Preserve PSU, case and slot flexibility for a future substantially higher-VRAM NVIDIA GPU
- Do not upgrade merely for higher gaming FPS
- Future AI value should be evaluated primarily in terms of VRAM, software compatibility and power/thermal requirements

### Networking and I/O

For a 7–10 year system, the motherboard should be evaluated for:

- wired Ethernet speed and controller quality
- Wi-Fi / Bluetooth support
- Linux/WSL friendliness where relevant
- USB4 / high-speed USB availability
- sufficient rear I/O
- usable PCIe expansion after storage devices are installed

## Decision philosophy

Each component review should answer:

1. What does the workload actually require?
2. What does the candidate provide?
3. Which features materially improve reliability, performance or longevity?
4. Which features are merely premium positioning?
5. What compatibility or topology constraints does the choice impose on other components?
6. Is there a cheaper alternative with no meaningful downside?
7. Is there a more expensive alternative with a concrete, defensible benefit?
8. What must be validated after purchase?
