# PSU Deep Dive

Status: **Selected — Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision**

## Decision

Use the **Seasonic VERTEX GX-1200**, specifically the current revision that is explicitly:

- **1200 W**;
- **ATX 3.1**;
- **PCIe 5.1**;
- supplied with a **600 W-capable 12V-2x6 GPU cable**;
- fully modular;
- backed by Seasonic's **12-year VERTEX warranty**.

The exact PSU decision is now closed. The remaining revision check is a **purchase/receipt acceptance check**, not an open architecture decision.

The build must **not** accept an ambiguous older VERTEX GX-1200 unit labelled ATX 3.0 / PCIe 5.0 / 12VHPWR simply because the family/model name is similar.

## Why 1200 W

The PSU is sized for the future workstation rather than the existing RTX 3060.

The explicit future design case remains one very high-power, high-VRAM GPU in the roughly **600 W** class. A deliberately conservative simultaneous-load envelope is approximately:

- future GPU: up to **600 W**;
- CPU/platform allowance: roughly **200–230 W**;
- motherboard, memory, SSDs, fans, USB and other devices: roughly **100–150 W**.

That produces a conservative sustained-system envelope around **900–980 W** before short-duration excursions.

A quality 1000 W ATX 3.1 PSU could operate many plausible configurations, but it would leave too little thermal, acoustic and aging margin for this explicit 600 W-GPU design case. The saving is not large enough to justify making a permanent component this tight.

**1200 W is therefore selected.**

1300–1600 W remains unnecessary for the intended single-GPU AM5 architecture. If the system genuinely evolves toward multiple 500–600 W accelerators, the platform itself should be reconsidered rather than pre-buying an oversized PSU today.

## Why the current VERTEX GX-1200

Seasonic's current official VERTEX GX specification provides:

- ATX 3.1 and PCIe 5.1 compliance;
- full 1200 W output in the 1200 W model;
- 12V-2x6 GPU cabling;
- 80 PLUS Gold efficiency;
- full modularity;
- 135 mm fluid-dynamic-bearing fan;
- Hybrid Silent Fan Control;
- OPP / OVP / UVP / SCP / OCP / OTP protections;
- compact **160 × 150 × 86 mm** dimensions;
- **12-year warranty**.

Official source:
- https://seasonic.com/vertex-gx/

Independent testing of the original GX-1200 platform family found strong build quality, full-power high-temperature operation, good ripple suppression, good hold-up behavior and correctly functioning main protections. The current ATX 3.1 revision remains the one to buy; platform lineage does not justify accepting old inventory when the modern revision is available.

## Revision transition and acceptance rule

Seasonic explicitly states that early VERTEX units shipped with **12VHPWR** and that the series transitioned to **12V-2x6** following the ATX standard update.

That history is why Romanian listings remain inconsistent.

Acceptance rule for the unit actually ordered/received:

1. retailer listing or packaging must say **ATX 3.1**;
2. the current product must be **PCIe 5.1** compatible;
3. the included GPU cable must terminate in **12V-2x6** at the GPU side;
4. reject old stock explicitly described as ATX 3.0 / PCIe 5.0 / 12VHPWR;
5. use only the Seasonic cable supplied/approved for this PSU family.

Some distributor listings identify the newer product as `GX 1200-ATX31`; that is useful corroborating evidence where present, but the actual ATX 3.1 / 12V-2x6 specification is the controlling requirement.

## 2026-08-31 Romanian purchase position

Procurement preference remains:

1. **PC Garage** first;
2. **eMAG** second;
3. another reputable Romanian retailer when the preferred sources cannot identify the current revision cleanly.

Current searches still do not expose a sufficiently unambiguous PC Garage or eMAG listing for the exact current revision.

A current **Altex** listing does explicitly advertise:

- **Seasonic Vertex GX-1200 ATX 3.1**;
- 1200 W;
- 80 PLUS Gold;
- full modularity;
- product shown in stock;
- price approximately **1,289.99 lei** at the latest indexed check.

Current source:
- https://altex.ro/sursa-pc-seasonic-vertex-gx-1200-atx-3-1-1200w-135mm-80-plus-gold-full-modular/cpd/VERTEXGX1200/

Therefore:

> Prefer PC Garage or eMAG if they can explicitly confirm the same current ATX 3.1 / 12V-2x6 revision at a sensible price. Otherwise, the explicit Altex ATX 3.1 listing is the current Romanian fallback rather than buying ambiguous old stock from a preferred retailer.

The revision is more important than a small retailer-price difference.

## Why not VERTEX PX-1200

The current VERTEX PX-1200 is also excellent:

- ATX 3.1 / PCIe 5.1;
- 12V-2x6;
- 80 PLUS Platinum;
- full modularity;
- 12-year warranty.

Official source:
- https://seasonic.com/vertex-px/

At the latest direct Romanian check, Media Galaxy listed the ATX 3.1 PX-1200 around **1,449.99 lei** but with stock exhausted, versus the GX around **1,289.99 lei** and available at Altex.

The PX premium mainly buys higher conversion efficiency and some potential acoustic/thermal-loss benefit. It does not change the wattage, connector architecture, protection requirement or warranty class. With the PX not currently purchase-ready and the GX already technically sufficient, there is no reason to defer the build for it.

Reopen GX versus PX only if, at actual checkout, a **known-current PX** is in stock and costs no more than roughly **100–150 lei** above a known-current GX. Even then the PX is an optional efficiency upgrade, not a reliability requirement.

## Other fallback

**Corsair HX1200i ATX 3.1 — `CP-9020307-EU`** remains the clearest non-Seasonic fallback because the current EU SKU is easy to identify.

It provides 1200 W, ATX 3.1 / PCIe 5.1-class support, 12V-2x6 cabling, Platinum efficiency, digital telemetry and a 10-year warranty.

It is not preferred over a correctly identified VERTEX GX because it is typically more expensive and does not provide a compelling reliability advantage for this build.

## Connector policy

The required **GPU-side connector is 12V-2x6**.

A PSU-side implementation that uses robust proprietary modular sockets is acceptable when it is Seasonic's designed cable topology; the PSU-side modular pinout is not universally standardized.

For a future high-power GPU:

- use only the PSU manufacturer's approved cable;
- fully insert and latch the 12V-2x6 connector;
- avoid a tight bend immediately at the GPU connector;
- re-check connector bend/side-panel clearance when the future GPU is selected;
- do not use third-party modular PSU cables unless explicitly certified for the exact PSU.

## Case and motherboard fit

The selected **Fractal Design North XL Mesh** provides roughly 290 mm PSU clearance. The 160 mm VERTEX GX therefore leaves substantial room for cable routing.

The **ASUS ProArt X870E-Creator WiFi** uses normal ATX motherboard power plus dual CPU EPS inputs. The VERTEX GX-1200 provides suitable motherboard and CPU power cabling without adapters.

The future GPU-side 12V-2x6 bend clearance remains the more important physical check and must be repeated when the future GPU is actually selected.

## UPS interaction

The selected **CyberPower CP1600EPFCLCD** is intentionally sized for the current RTX 3060 configuration, not for the PSU's 1200 W nameplate or the hypothetical future 600 W GPU.

The PSU only draws what the system actually consumes plus conversion losses. Reassess the UPS when the GPU changes materially or measured wall load approaches roughly 700–800 W.

## Assembly / validation

Before installation:

1. verify the received box/unit is the current **ATX 3.1** revision;
2. verify the supplied GPU cable is **12V-2x6**;
3. retain the exact PSU model/serial/warranty evidence;
4. use only the included/approved modular cables;
5. connect both motherboard CPU EPS inputs as appropriate;
6. inspect all connectors for full seating and strain-free routing;
7. enable Hybrid fan mode only if desired; either fan policy is acceptable as long as thermals remain normal.

## Selected conclusion

- **Exact PSU:** **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision — Selected**
- **Wattage:** 1200 W — Selected
- **Efficiency:** Gold is sufficient; Platinum is optional
- **Preferred retailers:** PC Garage first, eMAG second when the exact current revision is explicit
- **Current explicit Romanian fallback:** Altex ATX 3.1 listing, ~1,289.99 lei at latest check
- **PX-1200:** optional only if known-current, in stock and within roughly 100–150 lei of GX
- **Acceptance gate:** reject ambiguous ATX 3.0 / 12VHPWR old stock
