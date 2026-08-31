# PSU Deep Dive

Status: **Selected — be quiet! Pure Power 13 M 850W `BP027EU`**

## Decision

Select:

> **be quiet! Pure Power 13 M 850W — `BP027EU`**

Keep **Corsair RM850x 2024 850W `CP-9020270-EU`** only as a checkout-time fallback if availability, warranty or final delivered pricing becomes materially better.

The earlier 750 W baseline remains technically sufficient, but the selected 850 W unit wins because the observed Romanian premium over the corresponding 750 W model is small enough that the extra 100 W comes at negligible architectural cost.

## Why 850 W wins

The workstation no longer pre-provisions for a hypothetical future 500–600 W flagship GPU. Current GPU policy remains:

- reuse RTX 3060 12 GB for as long as useful/reliable;
- replace it only for a concrete need or failure;
- do not distort the rest of the build around unknown future flagship power requirements.

A premium 750 W supply is fully adequate for the current machine. However, the Pure Power 13 M 850 W has recently been only roughly **40–100 lei** above the 750 W model at Romanian retailers. That is within the project's explicit rule for accepting an 850 W upgrade.

The choice is therefore not based on speculative wattage. It is a small-premium purchase of useful electrical margin in a long-lived component.

## Selected unit qualities

The Pure Power 13 M 850W provides the characteristics required by the build:

- ATX 3.1;
- native 12V-2x6 / current PCIe GPU-power support;
- fully modular cabling;
- strong 12 V capability;
- 80 PLUS Gold-class efficiency with strong independent efficiency results;
- quiet/semi-passive fan implementation;
- mature LLC + synchronous-rectification + DC/DC topology;
- comprehensive mainstream protection set;
- 10-year manufacturer warranty;
- approximately 160 mm PSU length, comfortably compatible with the Pure Base 501.

Independent testing has shown strong transient handling, low ripple and exceptionally low acoustic output for the class. The minor-rail protection implementation is not perfect, but the relevant 12 V behavior and overall platform quality are strong enough to accept the unit.

## Fallback

**Corsair RM850x 2024 `CP-9020270-EU`** remains the preferred fallback.

It is also ATX 3.1, high quality and backed by a 10-year warranty. Its protection/fan implementation is somewhat more conservative in some respects, but the selected be quiet! unit currently wins on value and acoustics.

Do not substitute automatically. Re-evaluate only if the Corsair is within roughly **30–40 lei delivered** or has a clearly better retailer/warranty situation at checkout.

## Rejected sizing/classes

### 750 W

Still technically valid, but no longer the purchase target because the selected 850 W model costs only modestly more.

### 1000–1200 W

Not required. Buy only if a future concrete GPU replacement genuinely requires a PSU change. The former Seasonic VERTEX GX/PX-1200 targets remain superseded.

## Quality policy

Wattage remains secondary to quality. The purchase gate requires:

- exact model **`BP027EU`**;
- current/new retail unit;
- ATX 3.1 revision;
- native current-generation GPU-power cable supplied by the manufacturer;
- full modular cable set;
- normal Romanian/EU warranty path;
- no used/refurbished/open-box substitution without explicit review.

Do not reuse modular PSU cables from another PSU, even when connectors appear physically compatible.

## Future-GPU interpretation

The 850 W selection provides useful headroom for a substantially faster future GPU without claiming compatibility with every future flagship accelerator.

If a later GPU has unusually high board power or a vendor explicitly recommends more than the selected PSU can support, replace the PSU then rather than treating today's 850 W decision as an immutable lifetime constraint.

## UPS / mains interaction

There is no UPS requirement in the initial BOM. PSU sizing is independent of a hypothetical UPS wattage ceiling.

There is also no dedicated plug-in surge-protector requirement. The workstation may be connected to a properly earthed wall outlet or to a reputable ordinary 16 A Schuko power strip when additional outlets are needed. Revisit external mains protection only if actual power-quality problems appear.

## Commissioning

During assembly:

1. use only the modular cables supplied with this exact PSU;
2. connect the motherboard EPS/CPU power as specified by ASUS;
3. use the native GPU-power cable for any future GPU that requires it rather than adapters where avoidable;
4. verify fan behavior and absence of abnormal electrical/fan noise under representative load;
5. keep the PSU intake/filter unobstructed.

## Selected conclusion

- **PSU:** be quiet! Pure Power 13 M 850W `BP027EU`.
- **Status:** selected / closed.
- **Fallback:** Corsair RM850x 2024 850W `CP-9020270-EU`, price/warranty dependent.
- **750 W:** technically sufficient but no longer the purchase target.
- **1000–1200 W:** not required.
- **UPS:** not required initially.
- **Dedicated surge protector:** not required initially.
