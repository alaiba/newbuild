# CPU Deep Dive

Status: **Selected**

## Selected CPU / platform

- **CPU:** AMD Ryzen 9 9950X3D
- **Platform:** AMD AM5

This decision is closed unless the workload requirements materially change.

## Why this won

The Ryzen 9 9950X3D provides the best balance for the intended machine:

- very heavy Java development across very large codebases
- large Maven/Gradle builds and automated test suites
- IntelliJ IDEA and Android Studio
- containers, WSL2, local services, databases and occasional VMs
- strong foreground responsiveness for interactive development
- excellent gaming performance without optimizing the entire platform around gaming
- materially lower platform cost, power and cooling requirements than workstation-class alternatives
- a mainstream AM5 ecosystem with broad motherboard choice and simpler acoustics/thermals

The objective is a high-end general-purpose development workstation, not a dedicated build server or sustained-throughput compute node.

## Closest rejected alternative

### AMD Threadripper 9960X / TRX50

The 24-core Threadripper 9960X was the only workstation-class alternative retained for serious comparison.

It offers genuine advantages:

- 24 cores / 48 threads for highly parallel workloads
- four-channel DDR5 RDIMM memory
- ECC RDIMM support
- substantially greater PCIe connectivity
- higher sustained parallel throughput

However, the whole-platform premium is substantial. The relevant comparison is not CPU price alone: TRX50 also requires a materially more expensive motherboard and moves the machine toward a higher-power, workstation-oriented memory, cooling and platform architecture.

For this mixed workload, the additional throughput was not judged sufficient to justify the higher total cost of ownership and the loss of balance between workstation throughput, ordinary desktop use and gaming.

A useful economic framing from the comparison was that the 9960X would need to save a meaningful amount of genuinely blocked developer time, not merely post higher clean-build benchmark scores. Compilation/test time saved while the developer is doing something else has much lower value than reductions in latency on the critical iteration path.

## Other platforms rejected

- **Higher-core-count Threadripper 9000:** diminishing returns and increasing specialization beyond what this workload can credibly exploit.
- **Threadripper PRO / WRX90:** eight-channel memory, extreme capacity and PCIe expansion are not required by the current workload.
- **Intel workstation platforms:** no compelling balance of performance, platform cost and availability relative to the selected AM5 solution for this build.
- **ARM:** previously rejected because x86-64 provides the desired gaming compatibility and broad compatibility with development tools, virtualization, native dependencies, enterprise software and drivers.

## Reopen conditions

Reconsider the CPU/platform only if requirements materially change toward one or more of the following:

- sustained highly parallel compilation/test workloads that demonstrably scale well beyond 16 cores
- substantially larger VM/container consolidation workloads
- memory capacity or memory-bandwidth requirements that AM5 cannot satisfy well
- several high-bandwidth PCIe devices that cannot be accommodated without undesirable lane sharing
- use of the machine primarily as a local build/CI/compute server rather than as an interactive development workstation

## Downstream implications

All subsequent component research should assume **Ryzen 9 9950X3D + AM5** as a fixed input.

The next decisions should optimize around this platform, especially:

- motherboard/chipset and realistic PCIe/M.2 topology
- memory capacity, DIMM population, speed, stability and ECC considerations
- cooling and acoustic targets for sustained development loads
- PSU sizing with the existing GPU and plausible future GPU upgrades
