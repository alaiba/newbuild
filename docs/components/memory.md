# Memory Deep Dive

Status: **Purchased — Crucial Pro `CP2K24G56C46U5`, 48 GB as 2x24 GB / 1DPC / non-ECC**

## Final decision

Purchased from **CEL.ro** on **2026-09-01** for **2,899.00 lei**:

> **Crucial Pro `CP2K24G56C46U5` — 48 GB (2x24 GB) DDR5-5600 CL46, 1.1 V, non-ECC UDIMM**

Retailer page:
https://www.cel.ro/kit-ram-crucial-ddr5-48gb-5600mhz-cl46-2x24gb-pro-overclocking-pMCIzNzAsNCE-l/

Install the two DIMMs in **A2/B2** on the ASUS TUF GAMING B650E-E WIFI.

## Why 48 GB won

The 128 GB target was technically attractive but current pricing made it poor value. The 64 GB 2x32 GB option remained strong technically, but its premium over the 48 GB kit was disproportionate to the additional capacity.

With two DIMMs, reducing capacity to 48 GB does not intrinsically reduce CPU performance while the active working set fits. What 48 GB gives up is concurrency headroom: simultaneous JVMs, emulators, containers, VMs and filesystem cache before Windows begins reclaiming/paging.

The selected 48 GB configuration is therefore the utility-per-leu optimum for the initial build.

## Topology policy

Keep **two DIMMs / 1DPC**.

AMD officially rates Ryzen 9 9950X3D at DDR5-5600 with two DIMMs and lower rates with four populated DIMMs. A future capacity increase should therefore **replace** this 2x24 GB kit with a larger matched two-DIMM kit rather than adding a second pair.

Do not plan:
- 4x24 GB;
- mixed-capacity DIMMs;
- a four-DIMM path merely to preserve the purchased kit.

## Why this exact kit

The Crucial Pro kit aligns with the stability-first objective:
- matched 2x24 GB retail kit;
- DDR5-5600;
- CL46-class timings;
- conservative 1.1 V operating point;
- non-ECC unbuffered desktop DDR5;
- low-profile physical design;
- no need to depend on aggressive EXPO/XMP during commissioning.

## Physical compatibility

Selected/purchased cooler and case:
- Thermalright Phantom Spirit 120 standard;
- be quiet! Pure Base 501 Airflow `BG074`.

The Crucial Pro modules are low-profile and should fit cleanly with the dual-tower cooler.

## Arrival gate

Before installation, confirm:
- exact manufacturer code **`CP2K24G56C46U5`**;
- 48 GB total;
- two 24 GB modules;
- DDR5-5600 desktop UDIMM;
- non-ECC;
- new/sealed retail condition.

Reject a single 48 GB module such as `CP24G56C46U5` or another topology even if speed/timings appear similar.

## Bring-up policy

1. Install DIMMs in **A2/B2**.
2. Update motherboard to a current stable production BIOS.
3. First boot at **Auto/JEDEC**.
4. Confirm normal DDR5-5600 operation at conservative voltage.
5. Do not enable EXPO/XMP during initial commissioning unless later explicitly justified.
6. Run extended memory testing and representative Java/Android/WSL workloads.
7. Record BIOS/AGESA, trained timings and voltages.
8. Monitor actual committed memory during normal heavy work; this becomes the evidence for any future capacity replacement.

## Superseded memory plans

- 128 GB / 2x64 GB initial purchase;
- Crucial `CT2K64G56C46U5`;
- 64 GB / 2x32 GB as the preferred purchase target;
- 96 GB / 2x48 GB;
- any planned four-DIMM upgrade path;
- ECC as a hard purchase requirement.

## Final conclusion

- **Capacity:** 48 GB.
- **Topology:** 2x24 GB / 1DPC / A2+B2.
- **Exact kit:** Crucial Pro `CP2K24G56C46U5`.
- **Purchased:** CEL.ro, **2,899.00 lei**.
- **Operating point:** DDR5-5600 CL46-class, 1.1 V, Auto/JEDEC first.
- **ECC:** non-ECC.
- **Future upgrade:** replace the pair; do not add a second pair.
