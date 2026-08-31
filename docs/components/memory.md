# Memory Deep Dive

Status: **Selected — Crucial Pro `CP2K24G56C46U5`, 48 GB as 2×24 GB / 1DPC / non-ECC**

## Final decision

Use:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB (2×24 GB) DDR5-5600 CL46, 1.1 V, non-ECC UDIMM**

Install the two DIMMs in **A2/B2** on the selected ASUS TUF GAMING B650E-E WIFI.

## Why 48 GB won

The 128 GB target was technically attractive but current pricing around ~7.7k lei made it poor value. The 64 GB 2×32 GB option remained strong technically, but current pricing around ~4.7–4.8k lei is roughly 1.8–1.9k lei above the 48 GB Crucial Pro kit.

With two DIMMs, reducing capacity from 64/128 GB to 48 GB does not intrinsically reduce CPU performance while the active working set fits in memory. What 48 GB gives up is concurrency headroom: more simultaneous JVMs, emulators, containers, VMs and filesystem cache before Windows begins reclaiming/paging.

The selected 48 GB configuration is therefore the current utility-per-leu optimum.

## Topology policy

Keep **two DIMMs / 1DPC**.

AMD officially rates Ryzen 9 9950X3D at DDR5-5600 with two DIMMs and DDR5-3600 with four DIMMs. Therefore a future capacity increase must **replace** this 2×24 GB kit with a larger matched two-DIMM kit rather than adding a second pair.

Do not plan:

- 4×24 GB;
- mixed 24 GB + larger DIMMs;
- a four-DIMM path merely to preserve the initial kit.

If measured memory pressure later proves 48 GB insufficient, move directly to the best-value 2×32, 2×48 or 2×64 kit available at that time.

## Why this exact kit

The Crucial Pro kit aligns with the stability-first objective:

- matched **2×24 GB** retail kit;
- DDR5-5600;
- CL46-class timings;
- conservative **1.1 V** operating point;
- non-ECC unbuffered desktop DDR5;
- low-profile physical design;
- no need to depend on an aggressive EXPO/XMP profile during commissioning.

## Performance interpretation

When the full workload fits comfortably within 48 GB, expected application performance should be effectively the same class as larger two-DIMM configurations. The main differences versus 64/128 GB are:

- less filesystem cache;
- less room for multiple large JVM heaps;
- less VM/container/emulator concurrency;
- earlier onset of Windows memory pressure if the combined workload becomes too large.

This is a capacity/concurrency trade, not a deliberate CPU-speed trade.

## ECC verdict

Final configuration is **non-ECC**. ECC remains a desirable abstract capability, but current availability and economics do not justify distorting the selected capacity/topology.

## Physical compatibility

Selected cooler/case:

- Thermalright **Phantom Spirit 120 standard**;
- be quiet! **Pure Base 501 Airflow `BG074`**.

The Crucial Pro modules are low-profile and should fit cleanly with the dual-tower cooler.

## Bring-up policy

1. Install DIMMs in **A2/B2**.
2. Update motherboard to a current stable production BIOS.
3. First boot at **Auto/JEDEC**.
4. Confirm normal DDR5-5600 operation at the kit's conservative voltage.
5. Do not enable EXPO/XMP during initial commissioning unless later explicitly justified.
6. Run extended memory testing and representative Java/Android/WSL workloads.
7. Record BIOS/AGESA, trained timings and voltages.
8. Monitor actual committed memory during normal heavy work; this becomes the evidence for any future capacity replacement.

## Procurement note

Current Romanian reference price for `CP2K24G56C46U5` is approximately **2,899 lei**. Supplier is not architecturally fixed; choose a credible Romanian retailer with normal new-retail condition and warranty at checkout.

## Superseded memory plans

- 128 GB / 2×64 GB initial purchase;
- Crucial `CT2K64G56C46U5`;
- 64 GB / 2×32 GB as the preferred purchase target;
- 96 GB / 2×48 GB;
- any planned four-DIMM upgrade path;
- ECC as a hard purchase requirement.

## Selected conclusion

- **Capacity:** 48 GB.
- **Topology:** 2×24 GB / 1DPC / A2+B2.
- **Exact kit:** Crucial Pro `CP2K24G56C46U5`.
- **Operating point:** DDR5-5600 CL46-class, 1.1 V, Auto/JEDEC first.
- **ECC:** non-ECC.
- **Future upgrade:** replace the pair; do not add a second pair.
