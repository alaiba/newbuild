# PSU Deep Dive

Status: **1200 W ATX 3.1 architecture selected / exact model provisional pending retailer-revision verification**

## Selected PSU architecture

The build should use a **high-quality 1200 W ATX 3.1 / PCIe 5.1 PSU with a 600 W-capable 12V-2x6 GPU cable**.

This wattage is sized for the **future workstation**, not merely the existing RTX 3060.

Current provisional exact target:

- **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 revision**

Premium/reference alternatives:

- Seasonic VERTEX PX-1200, current ATX 3.1 revision
- Corsair HX1200i ATX 3.1 (2025), exact EU SKU `CP-9020307-EU`
- be quiet! Straight Power 12 1200 W, provided the exact current ATX 3.1 revision is verified at purchase

The previously discussed 1000 W class is no longer the preferred target. It is electrically possible for many plausible GPU configurations, but it leaves too little margin for the explicit 600 W-class future-GPU design case once CPU, motherboard, storage, fans, USB devices and transient behavior are included.

## 2026-08-31 purchase-readiness refresh

The **technical choice remains VERTEX GX-1200**, but the exact PSU is **not yet promoted to Selected** because current Romanian inventory has a revision-identification problem.

Seasonic's current official VERTEX GX product is explicitly:

- ATX 3.1;
- PCIe 5.1;
- 1200 W continuous output on the 1200 W model;
- supplied with a 600 W-capable 12V-2x6 cable;
- fully modular;
- 160 mm deep;
- backed by a 12-year manufacturer warranty.

However, Seasonic also explicitly states that VERTEX units were originally shipped with **12VHPWR** and were later transitioned to **12V-2x6** after the ATX-standard update. Romanian retailer/aggregator results in August 2026 still mix listings labelled **ATX 3.0 / PCIe 5.0 / 12VHPWR** with listings labelled **ATX 3.1** under essentially the same family/model name.

That creates a procurement risk: ordering by the text `VERTEX GX-1200` alone does not prove that the delivered unit is the current revision.

### Preferred-retailer result

Procurement policy remains:

1. **PC Garage** first;
2. **eMAG** second;
3. another reputable Romanian/EU seller only if the preferred sources cannot supply an unambiguous current revision at a sensible price.

As of this refresh, searchable results did **not** expose a PC Garage listing that could be independently verified as the current ATX 3.1 GX-1200. The identifiable eMAG VERTEX PX-1200 result is explicitly described as **ATX 3.0 / PCIe 5.0 / 12VHPWR**, so it is old-revision inventory for purposes of this build and should not be substituted merely because it is Platinum.

This is an inventory-identification issue, not evidence that PC Garage lacks the current product. At checkout time, the seller/product packaging must be inspected directly.

### Current Romanian price context

Current Romanian comparison results place VERTEX GX-1200 offers roughly around **1.1–1.3k lei**, but individual listings remain inconsistent about ATX 3.0 versus 3.1. Therefore the lowest displayed price is not automatically the correct product for this build.

The **revision takes precedence over a small price difference**.

### What would close the selection

Promote the current **Seasonic VERTEX GX-1200 ATX 3.1** to Selected once a preferred seller can confirm all of the following for the exact unit being ordered:

- packaging/product description says **ATX 3.1** and **PCIe 5.1**;
- the included GPU cable is **12V-2x6**, not merely the older 12VHPWR cable;
- normal Romanian/EU warranty path applies;
- product is new current stock rather than ambiguous old inventory.

If PC Garage can supply that unit near the prevailing market price, buy it there even if eMAG or another seller is slightly cheaper.

## Power model

### Current system

The initial RTX 3060 is modest relative to the selected PSU. The machine will therefore operate at a low fraction of PSU capacity during Phase 1.

This intentional oversizing is accepted because the PSU is a permanent component and replacing it later solely for a future GPU would create more cost and service risk than buying the correct long-term wattage now.

### Future design case

Use a **600 W GPU** as the upper design reference because the NVIDIA RTX PRO 6000 Blackwell Workstation Edition is a credible example of the single high-VRAM accelerator class the build is intended to preserve. NVIDIA specifies 600 W maximum board power and a PCIe CEM5 16-pin connector.

The Ryzen 9 9950X3D is a 170 W TDP processor. At the selected stock/conservative policy, practical sustained CPU package power should remain well below an unconstrained overclocking scenario, but PSU sizing should still leave margin above nominal TDP.

A conservative simultaneous high-load budget is approximately:

- future GPU: **up to 600 W**
- CPU/platform allowance: **~200–230 W**
- motherboard, RAM, SSDs, fans, USB and miscellaneous devices: **~100–150 W**

This gives a deliberately conservative sustained-system envelope around **900–980 W** before short-duration excursions.

Real development workloads will rarely hold both a 600 W GPU and the CPU at their maxima simultaneously, but the PSU should not depend on that assumption.

## Why 1200 W

### 1000 W

A quality ATX 3.1 1000 W supply could operate the system, especially with the current RTX 3060 or a lower-power future GPU. It is not the preferred long-term choice because a 600 W accelerator plus CPU/platform load can place the PSU close to continuous rated output under simultaneous stress.

That would reduce:

- thermal margin;
- acoustic margin;
- aging margin;
- room for future peripherals/storage;
- comfort around sustained compute workloads.

The saving is not large enough to justify designing the permanent PSU this tightly.

### 1200 W

**1200 W is the selected class.**

It provides roughly 20–30% nameplate headroom over the deliberately conservative future sustained-load model while keeping the PSU within a mainstream high-end ATX size and price class.

It also aligns well with modern ATX 3.x transient requirements. A compliant ATX 3.1 PSU is preferable to solving transient behavior merely by buying an older oversized PSU.

### 1300–1600 W

Not justified for the current architecture.

The build targets one very powerful GPU. Once the system genuinely requires several 500–600 W accelerators, AM5 itself should be reconsidered rather than pre-buying a huge PSU for a multi-GPU topology that is not part of the current design.

## ATX 3.1 / 12V-2x6 requirement

The permanent PSU should be:

- **ATX 3.1** compliant;
- **PCIe 5.1** compatible;
- equipped with a **600 W-capable 12V-2x6 GPU cable**;
- fully modular;
- equipped with complete OCP/OPP/OVP/UVP/OTP/SCP protections;
- rated for full output at elevated operating temperature by a credible vendor;
- backed by a long manufacturer warranty.

The GPU-side connector must be 12V-2x6. A PSU-side implementation using two robust 8-pin modular sockets is also acceptable when that is the manufacturer's designed cable topology; reliability depends on the complete validated PSU/cable system, not on requiring the PSU-side socket itself to be 16-pin.

Use only the PSU manufacturer's cable intended for that exact PSU family. Modular PSU-side pinouts are not universally standardized.

For a future 12V-2x6 GPU:

- fully insert and latch the connector;
- avoid force or tight bending immediately at the connector;
- verify cable routing against the final GPU width and case side-panel clearance;
- prefer a vendor-certified angled cable only if the physical layout actually requires it.

## Provisional target: Seasonic VERTEX GX-1200 ATX 3.1

Reasons it currently leads:

- 1200 W continuous output, including the full 1200 W on 12 V;
- current official revision is ATX 3.1 and PCIe 5.1;
- current official cabling includes 12V-2x6;
- fully modular;
- 135 mm fluid-dynamic-bearing fan;
- complete OPP/OVP/UVP/OCP/OTP/SCP protection set;
- 0–50 C specified operating range;
- compact **160 x 150 x 86 mm** enclosure;
- **12-year current Seasonic warranty** for VERTEX;
- mature independently tested underlying GX-1200 platform with full-power high-temperature operation, good ripple suppression, appropriately functioning main protections and quiet operation;
- Romanian price class remains reasonable for a permanent 1200 W high-end PSU.

Independent testing of the original ATX 3.0 GX-1200 platform found high build quality, full-power operation at 47 C, good ripple suppression, good hold-up behavior, low inrush current at 230 V and properly configured primary 12 V OCP/OPP. The current ATX 3.1 revision should still be treated as the product to buy; do not assume that an old ATX 3.0 box is equivalent merely because the underlying platform family is strong.

## Why not automatically buy VERTEX PX-1200

The current PX-1200 is an excellent alternative when the **actual unit is the current ATX 3.1 revision**:

- ATX 3.1 / PCIe 5.1;
- Platinum efficiency;
- 12V-2x6;
- 12-year warranty;
- same compact family form factor;
- strong electrical/acoustic platform lineage.

But the GX already has the same wattage, modern connector architecture, protection class and warranty. The PX premium mainly buys efficiency and somewhat better acoustics/thermal loss.

More importantly, current Romanian PX listings are also contaminated by old ATX 3.0/12VHPWR inventory. **Do not buy an old-revision PX instead of a current-revision GX simply because PX is the higher efficiency tier.**

Choose PX only when both units are known-current revisions and the PX price delta is small enough to make the extra efficiency/acoustic margin worthwhile.

## Other serious alternatives

### Corsair HX1200i ATX 3.1 — `CP-9020307-EU`

This is the clearest current-revision fallback because the exact EU SKU can be identified unambiguously.

Strengths:

- 1200 W;
- Intel ATX 3.1 certified / PCIe 5.1 compatible;
- 600 W-capable 12V-2x6 GPU cabling;
- Platinum efficiency;
- 140 mm FDB fan and zero-RPM behavior;
- 105 C Japanese electrolytic capacitors;
- digital monitoring/control;
- 10-year warranty;
- strong acoustics and high-temperature full-power capability in independent testing.

Current Romanian listings are roughly **1.4–1.6k lei** for `CP-9020307-EU`, making it modestly more expensive than typical VERTEX GX offers.

It is **not promoted ahead of the Seasonic solely because its SKU is easier to identify**. Independent 2025 testing praised its build quality, efficiency, noise, load regulation, hold-up time and normal-load transient response, but also noted less impressive 12 V/3.3 V behavior in the extreme ATX 3.1 transient tests and OCP/OPP thresholds that the reviewer would prefer to see lower under hot conditions. It remains a credible fallback, not an obvious reliability upgrade over a correctly identified current VERTEX GX.

### be quiet! Straight Power 12 1200 W

Technically attractive because current-revision listings provide:

- ATX 3.1 / PCIe 5.1;
- Platinum efficiency;
- multiple high-power GPU connectors;
- 10-year-class warranty/support;
- low-noise design.

But Romanian results still mix descriptions of the same family/article as ATX 3.0 and ATX 3.1. Therefore it does not solve the revision-identification problem cleanly enough to displace the current Seasonic target without exact seller confirmation.

## Efficiency policy

Do not select solely from 80 PLUS tier.

Gold versus Platinum primarily changes conversion loss, heat and potentially acoustics. It does **not** by itself establish build quality, transient behavior or protection quality.

The VERTEX GX's price, long warranty and good platform evidence make Gold acceptable. A Platinum model is worth buying when the price difference is modest, not as a hard requirement.

## Case interaction

The **Fractal Design North XL Mesh** provides up to approximately 290 mm PSU clearance, so the 160 mm VERTEX GX/PX fits with substantial cable-management margin.

Even the 200 mm Corsair HX1200i fits comfortably within the case envelope. Therefore PSU-body length does not distinguish the current candidates.

The more important future fit constraint is **GPU-side 12V-2x6 bend/side-panel clearance**, to be revalidated when the future GPU is actually selected.

## Motherboard interaction

The **ASUS ProArt X870E-Creator WiFi** uses standard ATX motherboard power and dual CPU EPS power inputs. The VERTEX GX-1200 provides two dedicated CPU/EPS cables, so no adapter or connector-sharing compromise is required.

## UPS interaction

UPS sizing should be performed against the **actual expected system load**, not simply by matching the PSU's 1200 W nameplate.

The PSU does not continuously draw 1200 W; it draws whatever the components demand plus conversion losses. The selected Phase-1 UPS remains intentionally sized for the current RTX 3060 configuration and must be reassessed when the GPU changes materially.

## Purchase / validation gates

Before promoting the exact PSU model to Selected:

1. locate a **current ATX 3.1 / PCIe 5.1 VERTEX GX-1200** at PC Garage first, eMAG second;
2. verify the exact box/listing states **ATX 3.1** and the supplied GPU cable is **12V-2x6**;
3. reject ambiguous old stock labelled only ATX 3.0 / PCIe 5.0 / 12VHPWR;
4. verify full Romanian/EU manufacturer warranty path;
5. compare current-revision GX/PX and `CP-9020307-EU` HX1200i pricing;
6. prefer GX unless a current PX is only modestly more expensive or the GX current revision cannot be sourced cleanly;
7. verify future GPU cable routing at the actual GPU purchase;
8. on assembly, inspect connector seating and strain-free cable routing.

## Current verdict

- **Wattage:** 1200 W — **Selected**
- **Standard:** ATX 3.1 / PCIe 5.1 + 600 W-capable 12V-2x6 — **Selected**
- **Provisional exact PSU:** **Seasonic VERTEX GX-1200, current ATX 3.1 revision**
- **Premium alternative:** Seasonic VERTEX PX-1200, current ATX 3.1 revision
- **Fallback with uniquely identifiable current EU SKU:** Corsair HX1200i `CP-9020307-EU`
- **Other alternative:** current-revision be quiet! Straight Power 12 1200 W
- **1000 W:** adequate for many configurations but rejected as the long-term target because of the explicit 600 W future-GPU design case
- **1300–1600 W:** unnecessary for the intended single-GPU AM5 architecture
- **Purchase status:** **do not order an ambiguously labelled VERTEX unit; exact model selection closes when a preferred retailer confirms current ATX 3.1/12V-2x6 stock**
