# PSU Deep Dive

Status: **1200 W ATX 3.1 architecture selected / exact model provisional**

## Selected PSU architecture

The build should use a **high-quality 1200 W ATX 3.1 / PCIe 5.1 PSU with a native 12V-2x6 GPU cable**.

This wattage is sized for the **future workstation**, not merely the existing RTX 3060.

Current provisional exact target:

- **Seasonic VERTEX GX-1200 ATX 3.1**

Premium/reference alternatives:

- Seasonic VERTEX PX-1200 ATX 3.1
- Corsair HX1200i ATX 3.1 (2025)
- be quiet! Straight Power 12 1200 W ATX 3.1, provided the exact current ATX 3.1 revision is verified at purchase

The previously discussed 1000 W class is no longer the preferred target. It is electrically possible for many plausible GPU configurations, but it leaves too little margin for the explicit 600 W-class future-GPU design case once CPU, motherboard, storage, fans, USB devices and transient behavior are included.

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

It also aligns well with modern ATX 3.x transient requirements. Intel's ATX design guidance explicitly defines short-duration power-excursion requirements because modern PCIe add-in cards can create very large transient demands. A compliant ATX 3.1 PSU is therefore preferable to solving transient behavior merely by buying an older oversized PSU.

### 1300–1600 W

Not justified for the current architecture.

The build targets one very powerful GPU. Once the system genuinely requires several 500–600 W accelerators, AM5 itself should be reconsidered rather than pre-buying a huge PSU for a multi-GPU topology that is not part of the current design.

## ATX 3.1 / 12V-2x6 requirement

The permanent PSU should be:

- **ATX 3.1** compliant;
- **PCIe 5.1** compatible;
- equipped with a **native 12V-2x6 cable** suitable for a 600 W-class GPU;
- fully modular;
- equipped with complete OCP/OPP/OVP/UVP/OTP/SCP protections;
- rated for full output at elevated operating temperature by a credible vendor;
- backed by a long manufacturer warranty.

Use the PSU manufacturer's native cable rather than a third-party modular cable. Modular PSU-side pinouts are not standardized.

For a future 12V-2x6 GPU:

- fully insert and latch the connector;
- avoid force or tight bending immediately at the connector;
- verify cable routing against the final GPU width and case side-panel clearance;
- prefer a vendor-certified angled cable only if the physical layout actually requires it.

## Provisional target: Seasonic VERTEX GX-1200 ATX 3.1

Reasons it currently leads:

- 1200 W continuous output, including the full 1200 W on 12 V;
- ATX 3.1 and PCIe 5.1;
- native 12V-2x6 support;
- fully modular;
- 135 mm fluid-dynamic-bearing fan;
- complete OPP/OVP/UVP/OCP/OTP/SCP protection set;
- 0–50 C specified operating range;
- compact **160 x 150 x 86 mm** enclosure;
- **12-year current Seasonic warranty** for VERTEX series;
- strong independent evidence for the underlying GX-1200 platform: full-power operation at high ambient temperature, good ripple suppression, correctly functioning main protections, quiet operation and successful testing with very high combined CPU/GPU loads;
- current Romanian pricing approximately **1.1–1.25k lei** for competitive offers.

The current official VERTEX GX product page is ATX 3.1 and uses 12V-2x6. However, older VERTEX inventory used ATX 3.0 / 12VHPWR while retaining very similar naming. **The exact unit received must therefore be verified as the current ATX 3.1 / 12V-2x6 revision before purchase acceptance.**

## Why not automatically buy VERTEX PX-1200

The PX-1200 is an excellent alternative:

- ATX 3.1 / PCIe 5.1;
- Platinum efficiency;
- Cybenetics Platinum / A-class noise rating;
- 12-year warranty;
- same compact 160 mm form factor;
- strong independent electrical/acoustic results.

But the GX already has the same wattage, connector architecture, protection class and warranty. Current GX pricing is materially lower. The PX premium mainly buys efficiency and somewhat better acoustics/thermal loss.

For this build, that premium is optional rather than required for reliability. Re-evaluate the exact price gap at purchase; choose PX if the delta becomes small.

## Other serious alternatives

### Corsair HX1200i ATX 3.1

Strong premium alternative:

- 1200 W;
- ATX 3.1;
- native 12V-2x6;
- Platinum efficiency;
- 140 mm FDB fan and zero-RPM behavior;
- digital monitoring/control;
- 10-year warranty;
- excellent independent efficiency, thermal and acoustic results.

Current Romanian pricing observed around **1.85–1.92k lei**, making it substantially more expensive than the VERTEX GX. Digital telemetry is useful but not important enough by itself to justify that premium.

### be quiet! Straight Power 12 1200 W

Technically attractive because the current official revision provides:

- ATX 3.1 / PCIe 5.1;
- two native 12V-2x6 connectors;
- Platinum efficiency;
- Japanese 105 C capacitors;
- 10-year warranty;
- very low-noise fan design.

Romanian search results still mix older ATX 3.0 article numbers with newer ATX 3.1 revisions. It remains a viable alternative, but the exact article/revision must be verified before comparing price.

## Efficiency policy

Do not select solely from 80 PLUS tier.

Gold versus Platinum primarily changes conversion loss, heat and potentially acoustics. It does **not** by itself establish build quality, transient behavior or protection quality.

The VERTEX GX's current low price, long warranty and good independent electrical behavior make Gold acceptable. A Platinum model is worth buying when the price difference is modest, not as a hard requirement.

## Case interaction

A 160 mm-deep VERTEX GX/PX is easy to accommodate in every current serious chassis candidate and leaves unusually generous cable-management room.

The exact case must still provide adequate side-panel clearance for a future 12V-2x6 cable at a very wide GPU. GPU connector bend clearance matters more than PSU-body clearance for the current shortlist.

## UPS interaction

UPS sizing should be performed against the **actual expected system load**, not simply by matching the PSU's 1200 W nameplate.

The PSU does not continuously draw 1200 W; it draws whatever the components demand plus conversion losses. The later UPS review should nevertheless account for a future high-power GPU configuration and the PSU's active-PFC input behavior.

## Purchase / validation gates

Before promoting the exact PSU model to Selected:

1. verify exact ATX 3.1 / PCIe 5.1 revision;
2. verify native 12V-2x6 cable and 600 W GPU suitability;
3. verify full Romanian/EU manufacturer warranty path;
4. refresh current GX/PX/HX1200i/Straight Power pricing;
5. verify case PSU clearance and future GPU cable routing;
6. avoid old-stock confusion where the same family name may refer to ATX 3.0 / 12VHPWR packaging;
7. on assembly, inspect connector seating and cable routing under the final GPU scenario.

## Current verdict

- **Wattage:** 1200 W — **Selected**
- **Standard:** ATX 3.1 / PCIe 5.1 + native 12V-2x6 — **Selected**
- **Provisional exact PSU:** **Seasonic VERTEX GX-1200 ATX 3.1**
- **Premium alternative:** Seasonic VERTEX PX-1200 ATX 3.1
- **Other alternatives:** Corsair HX1200i ATX 3.1; current-revision be quiet! Straight Power 12 1200 W
- **1000 W:** adequate for many configurations but rejected as the long-term target because of the explicit 600 W future-GPU design case
- **1300–1600 W:** unnecessary for the intended single-GPU AM5 architecture
