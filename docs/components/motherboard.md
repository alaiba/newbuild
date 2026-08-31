# Motherboard / Platform Deep Dive

Status: **Selected — ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**

## Fixed platform input

- CPU: **AMD Ryzen 9 9950X3D**
- Socket/platform: **AM5**
- Final RAM: **48 GB / 2×24 GB / 1DPC**
- Exact RAM: **Crucial Pro `CP2K24G56C46U5`**, non-ECC, DDR5-5600, conservative 1.1 V-class operation
- Case: **be quiet! Pure Base 501 Airflow `BG074`**
- GPU: existing RTX 3060, one-GPU architecture
- Storage: **one initial NVMe**, Crucial T710 2 TB in CPU-direct `M.2_1`; remaining M.2 slots left open
- Network: 1 GbE sufficient
- CPU operation: stock/conservative; no extreme OC objective

## Decision

Use **ASUS TUF GAMING B650E-E WIFI**, exact part **`90MB1LT0-M0EAY0`**.

This supersedes the short-lived ASUS TUF GAMING B850-PLUS WIFI selection. ECC and richer expansion had been among the stronger reasons to favor more expensive boards, but neither is a current requirement. Against the surviving workload needs, the B650E-E provides the better utility-per-leu result.

Do not confuse it with the separately sold **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**.

## Why B650 is enough

The build does not require:

- USB4 as a purchase gate;
- 5/10 GbE;
- CPU x8/x8;
- serious multi-GPU;
- a secondary PCIe x4 add-in path;
- multiple Gen5 storage devices;
- extreme-overclocking controls/power delivery.

The selected board therefore does not impose a meaningful workload compromise. CPU performance is unchanged, the one-drive storage topology is preserved cleanly, and the remaining premium B850 features do not map to an actual need.

## Memory support and firmware position

The board supports four DDR5 DIMM slots and substantial capacity headroom. The final configuration uses only **two 24 GB UDIMMs in A2/B2**, preserving 1DPC.

The selected Crucial Pro `CP2K24G56C46U5` is a matched 2×24 GB DDR5-5600 non-ECC desktop kit. Commissioning remains conservative: current stable BIOS, A2/B2, Auto/JEDEC first, conservative voltage, extended validation.

If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit rather than populating all four slots.

## PCIe / M.2 topology

With Ryzen 9000, the useful layout is:

- primary graphics slot: **CPU-connected PCIe 5.0 x16**;
- `M.2_1`: **CPU-connected PCIe 5.0 x4**;
- `M.2_2`: **CPU-connected PCIe 4.0 x4**;
- `M.2_3`: **chipset-connected PCIe 4.0 x4**;
- 4× SATA for later SSD/HDD capacity.

Recommended use:

| Connection | Planned role |
|---|---|
| Primary PCIe x16 | RTX 3060 / future single replacement GPU |
| `M.2_1` CPU x4 | **Crucial T710 2 TB primary SSD** |
| `M.2_2` CPU x4 | empty / future expansion |
| `M.2_3` chipset x4 | empty / future expansion |
| SATA | existing/later cold storage |

Using `M.2_1` for the T710 does not require reducing the primary GPU link.

### Secondary PCIe trade-off

The second physical x16 slot is chipset-connected but supports only **PCIe 4.0 x1** mode; there is also one PCIe 4.0 x1 slot.

This is accepted because the project has no planned need for a discrete high-speed NIC, HBA/RAID controller, second GPU, capture card or another high-bandwidth x4 add-in device.

If such a concrete requirement appears later, motherboard replacement can be reconsidered then rather than paid for speculatively today.

## VRM and CPU power delivery

The board's power-delivery specification provides comfortable margin for stock/conservative 9950X3D operation. The build deliberately does not reward phase-count marketing; unused current capability is not an invitation to increase power limits.

## Recovery / diagnostics / serviceability

Useful workstation features include:

- BIOS FlashBack;
- Q-LED CPU/DRAM/VGA/BOOT diagnostics;
- standard ATX layout and pre-mounted I/O shield;
- PCIe Q-Release and M.2 Q-Latch serviceability features;
- four SATA ports;
- CPU/CPU-OPT/AIO plus chassis-fan headers;
- rear USB-C;
- front USB-C header;
- 2.5 GbE and Wi-Fi 6E/Bluetooth without add-in cards.

These are materially more useful to this build than 5/10 GbE, x8/x8 or extreme-overclocking controls.

## ECC position

ECC is not a purchase requirement. The final RAM configuration is non-ECC. Do not substitute RDIMM/server memory; AM5 requires UDIMM.

## Alternatives considered

### MSI B850 GAMING PLUS WIFI `7E56-001R`

Strong fallback. It adds a genuine secondary PCIe x4 path, faster networking and newer wireless features, but none is currently required.

### ASUS TUF GAMING B850-PLUS WIFI `90MB1J30-M0EAY0`

Richer board, but the premium does not buy enough utility for this workstation. **Superseded on value.**

### ASUS ProArt X870E-Creator WiFi

Excellent board, but its old premium justification depended on much higher memory capacity, richer PCIe topology and workstation networking/expansion. **Superseded on value.**

## Procurement position

Refresh live price/stock immediately before checkout. Exact part **`90MB1LT0-M0EAY0`**, normal new retail condition and warranty path outrank a small saving.

EvoMAG currently appears to list both the selected B650E-E and the confusingly similar B650-E. The exact manufacturer part number must therefore be verified in-cart and again on the physical box.

## Commissioning

1. Verify exact board model/part number.
2. Install CPU, the selected two DIMMs in A2/B2 and only essential devices initially.
3. Flash a current stable production BIOS using normal update/FlashBack procedure as appropriate.
4. Load optimized defaults, then enable required UEFI/Secure Boot/TPM/SVM/IOMMU settings.
5. Keep CPU stock/conservative and memory Auto/JEDEC.
6. Validate cold boots, memory training, sustained CPU load, storage, GPU and sleep/resume.
7. Observe motherboard/VRM temperatures under representative sustained CPU load where sensors permit.
8. Enable BitLocker only after firmware/device stability is established.

## Selected conclusion

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` is the selected motherboard.**

It preserves every demonstrated workload requirement while avoiding premiums for ECC, networking, expansion and I/O capabilities the workstation does not currently need.
