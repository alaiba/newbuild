# PSU Deep Dive

Status: **Selected architecture — Seasonic VERTEX 1200 W ATX 3.1; GX-1200 baseline with PX-1200 preferred when the premium is small**

## Architecture decision

Use a **1200 W Seasonic VERTEX current ATX 3.1 / PCIe 5.1 unit with 12V-2x6**.

The build is sized for a future single high-power/high-VRAM GPU rather than only the current RTX 3060. A conservative future simultaneous-load envelope remains roughly:

- GPU: up to ~600 W;
- CPU/platform: ~200–230 W;
- motherboard/RAM/storage/fans/USB: ~100–150 W;
- sustained system envelope: roughly **900–980 W** before short transients.

A quality 1000 W PSU would be unnecessarily tight at that design point; 1300–1600 W does not buy enough useful margin to justify its extra cost/size for this single-GPU AM5 machine.

**1200 W remains the correct architecture.**

## Baseline exact model — VERTEX GX-1200

The current **Seasonic VERTEX GX-1200** provides:

- ATX 3.1 / PCIe 5.1;
- current 12V-2x6 GPU cabling;
- 1200 W continuous rating;
- 80 PLUS Gold efficiency;
- full modularity;
- 135 mm FDB fan / Hybrid Silent Fan Control;
- OPP / OVP / UVP / SCP / OCP / OTP protections;
- compact **160 × 150 × 86 mm** dimensions;
- **12-year warranty**.

Current explicit Romanian purchase path:

- **Altex VERTEX GX-1200 ATX 3.1**;
- about **1,289.99 lei** at the current reference;
- listing explicitly identifies ATX 3.1.

Official source:
- https://seasonic.com/vertex-gx/

## Premium opportunity — VERTEX PX-1200

The final value pass widened optimization to include **modest premium upgrades** when they improve useful lifetime value.

The current **VERTEX PX-1200** has the same core architecture and 12-year warranty but moves to **80 PLUS Platinum** efficiency. The improvement is not needed for compatibility or reliability, but it reduces conversion losses/heat throughout the life of a machine expected to spend many hours under sustained development load.

At the current Romanian reference:

- GX-1200: ~**1,289.99 lei**;
- PX-1200: ~**1,449.99 lei**;
- premium: roughly **160 lei**.

At only ~160 lei extra, PX has a favorable lifetime price/value ratio.

However, the explicit Altex/Media Galaxy ATX 3.1 PX listing is currently **out of stock**. Do not delay the workstation or add a new provider merely to chase Platinum efficiency.

### Purchase-time rule

Prefer a **known-current VERTEX PX-1200 ATX 3.1 / PCIe 5.1 / 12V-2x6** over GX when all of these are true:

1. it is actually in stock at one of the selected providers;
2. its exact current revision is unambiguous;
3. its premium over the equivalent known-current GX is **≤ ~200 lei**.

Otherwise buy the GX-1200.

This converts PX from a rejected luxury into a **conditional value upgrade**, without making procurement dependent on its availability.

Official source:
- https://seasonic.com/vertex-px/

## Why not larger or alternative PSUs

### 1300–1600 W class

Rejected for the current architecture. The machine is designed around one accelerator; if future needs truly require multiple 500–600 W GPUs, the AM5 platform itself should be reconsidered rather than pre-buying an oversized PSU now.

### be quiet! Straight Power 12 1200 W

Technically excellent: ATX 3.1, Platinum-class efficiency, high-quality components and long warranty. It remains a credible fallback, but current price differences are too small to justify giving up the longer Seasonic 12-year warranty and the already-clean revision/purchase path.

### Corsair HX1200i ATX 3.1

Also credible, but typically more expensive without a material reliability advantage for this build.

## Revision transition and hard acceptance gate

Seasonic explicitly states that early VERTEX units shipped with **12VHPWR** and later transitioned to **12V-2x6** after the ATX standard update. Therefore model family name alone is not sufficient.

For **either GX or PX**, the ordered/received unit must pass:

1. listing/box says **ATX 3.1**;
2. **PCIe 5.1** compatibility;
3. supplied GPU cable is current **12V-2x6**;
4. reject explicit old ATX 3.0 / PCIe 5.0 / 12VHPWR stock;
5. use only Seasonic-approved modular cables;
6. retain exact model/serial/warranty evidence.

## Case / motherboard fit

Both current 1200 W VERTEX models use the compact 160 mm depth class and fit comfortably inside the selected Fractal North XL Mesh. The ProArt's ATX and CPU EPS requirements are covered without adapters.

Future GPU connector bend/side-panel clearance must be rechecked when that GPU is selected.

## UPS interaction

The PSU can deliver 1200 W but only draws what the system consumes plus conversion losses.

The selected **CyberPower PR1500ELCD 1350 W UPS** now provides comfortable real-power margin for the current machine and a credible future 900–980 W workstation load, removing the mismatch that existed when the 1000 W CP1600 UPS was selected.

## Selected conclusion

- **Architecture:** 1200 W ATX 3.1 / PCIe 5.1 / 12V-2x6 — Selected
- **Baseline:** Seasonic **VERTEX GX-1200** — purchase-ready
- **Preferred conditional upgrade:** Seasonic **VERTEX PX-1200** when known-current stock is available at **≤~200 lei premium**
- **Do not delay the build for PX**
- **Current practical route:** Altex GX-1200 ~1,289.99 lei while PX is out of stock
- **Warranty:** 12 years for both current VERTEX models
- **Receipt gate:** reject ambiguous/old ATX 3.0 / 12VHPWR inventory
