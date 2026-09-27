# Scenario Brief — Chien Feng Precision Semiconductor

**Read this before you build the register.** Your group is the risk team performing the annual physical-and-cybersecurity risk assessment for a mid-size semiconductor subcontractor. Everything you need to score a risk is in here. Anything not stated is yours to infer *and to write down as an assumption*.

---

## The company

**Chien Feng Precision Semiconductor Co., Ltd.** (鍊豐精密半導體) — a wafer fabrication and packaging subcontractor in the **Taichung** metropolitan area, in the Science Park corridor.

| | |
|---|---|
| **Headcount** | ~400 (260 production, 60 process engineering, 45 office/administration, 35 contract maintenance and facilities) |
| **Site** | One leased campus building, 3 floors + roof plant deck. Leased, not owned — the landlord controls the building shell, roof membrane, and main incoming power. |
| **Process** | Back-end packaging and test: wafer thinning, dicing, wire bond, final test. **No front-end fab, no EUV, no cleanroom lithography** — this is a subcontractor, not a device maker. |
| **Operating hours** | 8-hour staffed days, two shifts, 07:00–18:00 weekdays. **Skeletal crew overnight** (2 security guards, 1 facilities technician). Production runs unattended overnight and weekends. |
| **Certification** | ISO 9001, IATF 16949 (automotive), customer audits twice a year. Customer audit findings are a commercial risk, not just a security one. |

## Physical environment

- **Shared building surfaces.** Chien Feng occupies floors 2–3. **Floor 1 is a neighbouring tenant** (a logistics office) with **its own separate lobby, but a shared loading dock and a shared service corridor on the west side.** The dock door is one badge reader for both tenants. The service corridor has a fire door between the tenants that is alarmed but not badge-controlled.
- **Perimeter.** A 2.4 m fence with a sliding vehicle gate on the north side. The fence abuts a public road on three sides. A motorcycle parking area sits **inside** the fence but **outside** the building, with no camera coverage — staff park there, so it is effectively a public-adjacent space with company property in it.
- **Roof and flood exposure.** Taichung is typhoon country and sits on a low-lying basin. The building has a **flat roof with a plant deck**, and the **roof access door is secured with a padlock** (key shared by 5 facilities staff). The site is in a documented **flood hazard zone**: the loading dock threshold is 4 cm above the surrounding grade, and the site's own drainage was regraded in 2024 and is adequate. Records storage (paper and one tape archive) is on the **ground floor** in room G-07.
- **Power and environment.** The site takes **normal commercial power with no on-site generation and no uninterruptible supply for production equipment.** The landlord supplies a single 800 kVA transformer. There is a small UPS for the network core, sized for ~15 minutes.
- **Utilities.** Ultra-high-purity water, bulk nitrogen, and compressed air are all landlord-supplied through shared risers. Chemical storage ( acids, plating chemistry, cleaning solvents ) is in a ventilated cabinet in room G-12, ground floor.

## People and access control

| Population | Badge | Notes |
|---|---|---|
| Employees | Individual proximity badge, photo | 400 badges issued |
| Contract maintenance technicians | Individual badge, **escort-required, no unescorted access to production areas** | 35 badges, issued by facilities |
| Cleaners | **One shared badge** | 3 badges total, handed over at shift change |
| Security guards | Individual badge | 2 guards, rotating 12-hour shifts |
| Visitors | **No badge.** Sign in at reception on paper, escorted at all times, badge returned at exit | Paper sign-in sheet, not digital |

- **Doors.** MAIN-EAST and MAIN-WEST (two ground-floor staff entries, badge-only, no reception), LIB-ENTRY (library, badge), SCI-ANNEX (an adjacent lab building connected by a single badge-controlled door, shared with a university partner who has their own badge population), and **SERVER-RM** (server room, badge + PIN, in the basement).
- **The server room is in the basement.** Flood exposure applies to it. It has no water sensor.
- **Badge system.** The badge system is on-premise: a dedicated controller per door, logs retained **30 days**, then overwritten. No tailgating detection, no forced-door alarm on MAIN-EAST or MAIN-WEST, no live video integration. The card reader firmware is at version 3.2.1; the vendor released 4.0.0 in 2025 and the upgrade has not been scheduled because it requires a production shutdown window.
- **CCTV.** 14 cameras, 30-day retention on a DVR in the security office. Coverage is good at the north gate and reception, and **absent** from the motorcycle parking area, the west service corridor, and the SERVER-RM corridor. The DVR is on the same network segment as office desktop PCs.

## IT and OT environment

- **Two networks, one switch room.** A corporate office network and a production/OT network. They are **logically separated but share the same basement switch room and the same physical cable tray**, and the OT firewall has a single maintenance-port bypass that facilities staff use for vendor laptop drops.
- **Recipe and process data.** Process recipes, test programs, and yield data live on a file server in the basement server room. **The server room has single-factor badge access and is unattended overnight.** Backups run nightly to an external USB disk in the same room.
- **R&D.** The process engineering team holds customer-specific package designs and test programs for two automotive customers. These are the company's primary IP. Test programs are distributed to test stations on shared removable media.

## Commercial context

- The two automotive customers audit annually and have both flagged test-program version control as a finding in the last cycle.
- The landlord has proposed converting the west service corridor to a shared mechanical room access in the next lease renewal. The fire door's alarm would need to be reclassified.
- Insurance requires a documented physical security assessment for the fab contents policy. The register you are building is that document's supporting analysis.

---

## What to do

1. **Enumerate 8 or more assets.** Below is a starter list. You are expected to *go beyond it* — the gallery walk rewards an asset other groups missed. Use it to aim, not to stop.

| # | Asset to consider | What makes it interesting |
|---|---|---|
| 1 | The basement server room (SERVER-RM) | Single-factor access, no water sensor, backups in the same room as the thing they back up, network segment shared with office desktops |
| 2 | Test program and recipe data on the file server | The company's primary IP; on removable media; the customers have already flagged it |
| 3 | The shared loading dock | One badge reader for two tenants; 4 cm flood threshold; shared-supply custody at the threshold |
| 4 | The west service corridor and its fire door | Alarmed, not badge-controlled; cross-tenant; a reclassification is pending |
| 5 | The roof access door and the plant deck | Padlock with a 5-person key ring; typhoon exposure on a flat roof |
| 6 | The cleaner badges | Three shared credentials, handed over at shift change, coverage of the whole building including G-07 records |
| 7 | The visitor sign-in sheet | Paper, unbacked up, no badge issued, escort only, names and companies of every visitor to a certified site |
| 8 | The motorcycle parking area | Inside the fence, no camera, staff property, effectively public-adjacent |
| 9 | Records storage in room G-07 | Ground floor, flood zone, paper and one tape archive |
| 10 | The OT firewall maintenance-port bypass | Vendor laptops onto the production network, in the shared switch room |
| 11 | The badge system firmware (3.2.1) | Upgrade requires a production shutdown — availability vs. security tradeoff, a real register entry |
| 12 | The CCTV DVR on the office network segment | 30-day retention, itself an asset on a segment it should not be on |
| 13 | Chemical storage G-12 | Ground floor, flood zone, ventilation, shared landlord risers |
| 14 | The 800 kVA single-transformer supply | No backup generation, no UPS for production — a 3-hour outage is a scrap event |
| 15 | The SCI-ANNEX shared door | Two badge populations, one reader, university partner with independent access provisioning |
| 16 | The badge log retention (30 days) | Every detection discussed in Unit 2 depends on logs that survive. 30 days is short. |

2. **Spread the register.** Do not submit eight variations of the same server. A group that scores the file server, the backup disk, the removable media, the test stations, and the removable-media laptop separately is doing this right — same system, genuinely different risks.

3. **For each asset:** vulnerability, likelihood 1–5 with a reason, impact 1–5 with a reason in real units, inherent risk, one specific costed control, residual risk with the axis you changed and the control's limits, and an owner.

4. **Write your assumptions down.** If you inferred something not stated in this brief, say so. An assumption written down is defensible in the gallery walk; an assumption you kept in your head is not.

## Two warnings

- **Do not treat "hacker" as a vulnerability.** A vulnerability is the weakness. "A phishing email to a process engineer is a routine occurrence here" is a likelihood *reason*. "An attacker" is a threat, and it belongs in neither column.
- **Do not let a control address the asset instead of the vulnerability.** The most common error in the room, per the lesson, is a control that sounds sensible and does not touch the named weakness.
