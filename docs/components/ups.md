# UPS / Power Protection Deep Dive

Status: **No UPS in initial BOM; point-of-use surge protection selected**

## Decision

Do **not** buy a UPS for the initial workstation.

The previous CyberPower PR1500ELCD selection is superseded.

The user does not need continuity through outages: a laptop is available, and short outages are acceptable operationally. A large battery-backed UPS therefore does not provide enough value to justify its purchase price, battery maintenance and eventual replacement.

## What a UPS would solve

A UPS is useful for:

- riding through brief outages;
- giving time for graceful shutdown;
- reducing interruption to long-running jobs;
- voltage regulation on suitable line-interactive models.

Those benefits are currently low priority for this workstation.

## What matters for hardware protection

The more relevant physical-hardware concern is transient overvoltage/surge rather than the simple disappearance of mains power.

Under the explicit constraint that the electrical installation itself will not be modified, use a **reputable plug-in surge protector / surge-protected power strip** between the wall outlet and the workstation.

Prefer a device with:

- clear surge-protection status indicator;
- Schuko/Type-F grounding appropriate for the local installation;
- reputable manufacturer and safety certifications;
- sufficient current/power rating for the workstation and connected displays/peripherals;
- replaceable/discard-on-expiry policy when the protection indicator shows the suppression elements are exhausted.

## Important limitation

Point-of-use surge protection is a practical compromise, not equivalent to coordinated building-level Type 1/Type 2 surge protection.

Its effectiveness depends on a sound protective-earth connection. A plug-in protector cannot correct missing/poor earthing or absorb every severe event such as a close/direct lightning event.

No electrical-installation modifications are required by this PC project.

## Outage policy

Occasional short outages are accepted. Consequences are primarily operational/data-consistency risks rather than expected physical destruction of PC components.

Mitigations remain:

- version control;
- independent backups;
- mature filesystems/applications;
- avoiding firmware/BIOS updates during obviously unstable mains conditions;
- saving work normally;
- using the laptop when continuity matters.

If actual use later shows that abrupt shutdowns are annoying or harmful to VM/database workflows, add a **modest UPS sized from measured workstation wall consumption**, not from PSU nameplate wattage.

## Superseded selection

The following are no longer purchase targets:

- CyberPower PR1500ELCD 1500 VA / 1350 W;
- the earlier 1000 W-class UPS candidates;
- sizing a UPS around a hypothetical 900–980 W future workstation;
- buying a UPS mainly for surge protection.

## Selected conclusion

- **UPS:** none initially.
- **Continuity requirement:** none.
- **Point-of-use protection:** reputable surge-protected plug/power strip.
- **Electrical installation changes:** none required by this project.
- **Future UPS:** reconsider only if real observed outages/workloads create a concrete need.
