# A.7 Physical controls

The 14 controls governing the physical protection of premises, equipment, and media. Many small and remote-first teams don't run their own facilities at all; where that's the case, each control below notes how the same intent applies when physical security is largely inherited from a landlord, co-working provider, or cloud/hosting provider rather than self-managed.

---

### A.7.1 Physical security perimeters

**What it requires:** Physical boundaries must be defined around any space that houses information assets or processing equipment, so that protection can be applied consistently within that boundary.

**Implementation guidance:**
- Draw an explicit line around each in-scope location (offices, storage rooms, comms/server rooms) and document it; don't leave "the perimeter" implicit.
- Assign a named owner accountable for keeping perimeter controls current as the organisation's footprint changes.
- Apply layered controls proportionate to what's inside: a locked door is enough for a general office, a card-controlled room is warranted for anything holding concentrated sensitive data.
- If you don't own or manage your own premises (a co-working space, a shared building, a serviced office), treat the landlord's or operator's controls as inherited rather than something you re-build. Get a written summary of what they provide and document explicitly what remains your responsibility.
- Re-assess the perimeter definition whenever the office footprint changes (new site, sublease, move to hybrid/remote).

**Evidence an assessor would want to see:**
- A documented physical security policy/standard naming the accountable owner.
- A current site list showing which premises are in scope and who controls physical security at each.
- A vendor security summary or attestation for any inherited premises.

### A.7.2 Physical entry

**What it requires:** Entry into secure areas must be controlled so that only authorised people can get in, with a mechanism to verify who is entering.

**Implementation guidance:**
- Choose an entry control appropriate to the site (key card, PIN, biometric, staffed reception, or a combination) and apply it consistently.
- Run a visitor process: sign-in, visible identification, and escort for anyone who isn't staff.
- Maintain a list of who holds physical access credentials and review it on a schedule, removing access promptly when someone leaves or changes role.
- Where entry is managed by a landlord or co-working operator rather than by you directly, confirm, and periodically re-confirm, that their entry controls meet your minimum bar instead of assuming they do.

**Evidence an assessor would want to see:**
- A policy describing the entry control mechanism per site.
- Swipe/badge access logs, a CCTV coverage description, staffed reception hours, or visitor sign-in log screenshots, whichever apply to the site.
- A periodic access-list review record.
- Written confirmation from a shared-site provider that their entry controls meet your requirements.

### A.7.3 Securing offices, rooms and facilities

**What it requires:** Offices and specific rooms or facilities that hold sensitive information or systems must have physical protections designed in, not bolted on as an afterthought.

**Implementation guidance:**
- Identify any rooms or zones that need stronger protection than open-plan space (server/comms rooms, records storage, rooms used for sensitive discussions) and apply extra controls (locks, restricted access) to them specifically.
- Avoid signage or labelling that identifies sensitive processing areas to people outside the organisation.
- If your organisation doesn't run its own facility, document clearly which office-level controls are inherited from the landlord or co-working provider, and which (e.g., a locked cabinet inside your own suite) are your responsibility.
- Build a physical-security check into the process for standing up any new office or site.

**Evidence an assessor would want to see:**
- An inventory of secure rooms/areas and the specific controls applied to each.
- Landlord/provider confirmation of baseline facility controls where premises are shared or leased.
- A new-site setup checklist that includes physical security.

### A.7.4 Physical security monitoring

**What it requires:** Premises must be actively and continuously monitored so unauthorised physical access attempts can be detected, not just prevented on paper.

**Implementation guidance:**
- Put continuous monitoring in place appropriate to the site: CCTV, alarm systems, after-hours or concierge security, monitored visitor sign-in.
- For shared or leased premises, get assurance (a contract clause, a compliance certificate, or a vendor summary) that the landlord or co-working operator runs equivalent monitoring, rather than duplicating it yourself.
- Define who reviews monitoring alerts and how a suspected physical security incident gets escalated.
- Retain monitoring records (CCTV footage, entry logs) for a defined period so they're available if an investigation is needed.

**Evidence an assessor would want to see:**
- A list of monitoring controls per site with the responsible party noted (in-house vs. provider).
- Sample retained monitoring/access logs.
- An escalation process for physical security alerts.

### A.7.5 Protecting against physical and environmental threats

**What it requires:** Premises and infrastructure must be protected against natural disasters and other physical or environmental hazards: fire, flood, extreme weather, and similar.

**Implementation guidance:**
- Identify the realistic environmental threats for each site (fire, flood, severe weather, power loss) and confirm mitigations actually exist rather than assuming they do.
- Where premises are shared or leased, rely on and document the landlord's or provider's safety rules (no-smoking policy, restrictions on hazardous/flammable materials, fire suppression systems) instead of building parallel controls.
- For infrastructure hosted with a cloud or data-centre provider, reference their published physical and environmental control programme. Don't attempt to independently verify what you can't access; keep their compliance documentation on file instead.
- Re-check that these third-party references are still current at least annually, or whenever you change provider.

**Evidence an assessor would want to see:**
- A reference copy of the hosting/cloud provider's data-centre compliance documentation. For most teams, this is satisfied by citing the provider's own third-party audit report (their SOC 2 or ISO certificate) rather than independently re-testing their facility.
- A copy of the landlord's or co-working provider's relevant safety/house rules, plus a floor plan and evacuation diagram where applicable.
- An annual review note confirming these references remain valid.

### A.7.6 Working in secure areas

**What it requires:** Staff must follow specific behavioural rules that protect information while they're working in or around secure areas.

**Implementation guidance:**
- Set clear expectations: lock or log off workstations when stepping away, keep sensitive documents secured rather than left out, and don't bring unauthorised visitors into restricted areas.
- Fold these expectations into a policy that's covered at onboarding and reinforced periodically, rather than left as an unwritten norm.
- Extend the same principles to remote and home working; a "secure area" isn't only a physical office.
- Do occasional informal spot-checks to confirm the policy is actually being followed, not just acknowledged.

**Evidence an assessor would want to see:**
- A policy covering secure-area behaviour, with staff sign-off/acknowledgement.
- Onboarding or training material showing the policy is communicated.
- Notes from a periodic compliance walk-through.

### A.7.7 Clear desk and clear screen

**What it requires:** Desks must be kept clear of sensitive papers and removable media, and screens must be secured against casual viewing, whenever unattended.

**Implementation guidance:**
- Enforce a short auto-lock timeout on all devices used to handle company or customer information.
- Require sensitive papers and removable media to be stored in a locked drawer or cabinet rather than left on a desk, particularly overnight.
- Apply the rule everywhere work happens (shared desks, hot-desking, and remote settings), not only a fixed office.
- Put the requirement in a written policy new starters acknowledge, and repeat it periodically as a reminder.
- Include printer and photocopier output trays in the same rule: printed sensitive material left unattended is the same exposure as a cluttered desk.

**Evidence an assessor would want to see:**
- A written clear-desk/clear-screen policy with staff acknowledgement.
- A device configuration standard showing the enforced auto-lock timeout, plus photographic spot-check evidence of a clear desk in practice.
- Periodic walk-through or spot-check notes.

### A.7.8 Equipment siting and protection

**What it requires:** Equipment must be physically positioned and protected to reduce the risk of damage, loss, or unauthorised viewing/access.

**Implementation guidance:**
- Position screens and equipment to avoid casual overlooking ("shoulder surfing") in shared, open-plan, or public-facing areas.
- Use surge protection for equipment that's sensitive to power fluctuations.
- Treat siting as one more layer on top of your access-control and clear-screen rules, not a substitute for either.
- In shared workspaces where you don't control the layout, factor the provider's constraints into what can and can't be displayed or left visible.

**Evidence an assessor would want to see:**
- An asset register noting equipment location and any special siting considerations.
- Photos or floor-plan notes for sensitive-equipment placement, where applicable.
- A record of surge-protection devices in use.

### A.7.9 Security of assets off-premises

**What it requires:** Equipment taken off company premises must be protected to a standard equivalent to what applies on-site.

**Implementation guidance:**
- Require prior approval before equipment or media is taken off-site.
- Set clear expectations for staff using mobile equipment off-site: never leave devices unattended in public or in vehicles, use any carry case or lock provided, and follow the manufacturer's care and security guidance.
- Cover home and remote-working equipment under the same acceptable-use and security expectations as in-office equipment.
- Maintain full-disk encryption and remote-wipe capability on all portable devices, so loss or theft off-site doesn't automatically become a data breach.

**Evidence an assessor would want to see:**
- An acceptable-use or mobile-equipment policy covering off-site use.
- Approval records for equipment taken off-site, where required.
- MDM/encryption configuration confirming portable devices are covered.

### A.7.10 Storage media

**What it requires:** Storage media must be managed securely across its whole lifecycle (acquisition, use, transport, and disposal) in line with the organisation's information classification rules.

**Implementation guidance:**
- Keep an asset register that includes storage media and removable devices, each with a named owner.
- Apply your information classification scheme to decide the handling and protection level required for each type of media (encryption, restricted access, transport controls).
- Require authorisation before media leaves the premises, with controls scaled to the sensitivity of what it holds.
- Back classification and handling rules with a clear, communicated acceptable-use policy so they're actually followed day to day, not just documented.
- Feed end-of-life media into a formal secure disposal process rather than discarding it ad hoc.

**Evidence an assessor would want to see:**
- An asset register including storage media entries with assigned owners.
- An information classification and handling policy.
- Approval records for media taken off-site.
- An encryption standard applied to storage media.

### A.7.11 Supporting utilities

**What it requires:** Information-processing facilities must be protected against disruption from power, water, or other utility failures.

**Implementation guidance:**
- For self-managed or leased premises, confirm what utility resilience the building or landlord already provides (backup power, emergency lighting, utility shut-off switches) and document any gap you still need to close yourself.
- Keep emergency contact details and utility-outage procedures somewhere staff on-site can reach them quickly.
- For cloud-hosted infrastructure, reference your provider's published resilience and compliance documentation for power, cooling, and utility redundancy rather than trying to independently verify or duplicate it.
- Re-confirm utility-related contacts and procedures are current after any office move or change of hosting provider.

**Evidence an assessor would want to see:**
- A reference copy of the hosting/cloud provider's published resilience documentation.
- The building's emergency procedures, showing utility shut-off points and emergency contacts.
- A review note confirming the above is still current.

### A.7.12 Cabling security

**What it requires:** Cables carrying power, data, or communications must be protected from interception, interference, or physical damage.

**Implementation guidance:**
- Where the organisation relies mainly on wireless networking rather than fixed data cabling, document that this control largely doesn't apply in the traditional sense, and redirect the effort into wireless network security instead (strong encryption standards, a segmented guest network, rogue access-point detection).
- For any physical cabling you do control (network switches, patch panels, power runs), keep it in a locked or restricted space and label it clearly to prevent accidental disconnection or tampering.
- Where a landlord or shared-workspace provider owns the building's cabling infrastructure, treat their controls as inherited and get confirmation they meet a reasonable baseline.
- Separate power and data cabling where practical to reduce interference risk.

**Evidence an assessor would want to see:**
- A network architecture note describing reliance on wireless vs. wired connectivity.
- A wireless network security configuration standard.
- Confirmation from the building or provider on cabling infrastructure controls, where applicable.

### A.7.13 Equipment maintenance

**What it requires:** Equipment must be properly maintained so its availability, integrity, and the confidentiality of what it processes are preserved over its working life.

**Implementation guidance:**
- Maintain a documented maintenance procedure covering hardware servicing, firmware/OS patching, and vendor-supplied updates.
- Track maintenance activity against the asset register so nothing falls through the cracks.
- Set a minimum patching and update cadence based on how critical each asset is.
- Where a third party performs maintenance or repairs, bind them to confidentiality and security expectations, and protect or remove storage media before hardware leaves the premises for external repair wherever that's feasible.

**Evidence an assessor would want to see:**
- A documented equipment maintenance procedure.
- Maintenance and patch records linked to the asset register.
- Contract terms with any third-party maintenance provider covering confidentiality and security.

### A.7.14 Secure disposal or re-use of equipment

**What it requires:** Before equipment or media is disposed of or reassigned, it must be verified as wiped of sensitive data and licensed software.

**Implementation guidance:**
- Maintain a documented disposal/re-use procedure requiring verified data wiping (or physical destruction for media that can't be reliably wiped) before anything leaves the organisation or is handed to someone else.
- Use a certified disposal vendor or a documented internal wiping standard, and keep a certificate or log confirming destruction or successful wipe for each asset.
- Cover the full range of media, not just obvious "computers": phones, USB drives, backup media, and printers/copiers with internal storage all count.
- Update the asset register to reflect disposal or re-use so retired equipment doesn't linger as "in service."
- Remove or reassign software licence entitlements as part of the same process so licences aren't silently carried over to a new owner.

**Evidence an assessor would want to see:**
- A documented disposal/re-use procedure.
- Wipe or destruction certificates/logs per asset.
- An updated asset register showing disposal status.
- A contract with the disposal vendor covering their data-destruction obligations, if one is used.

---

## Adapt this to your context

- **Fully remote, no owned premises?** Most of A.7 still applies, just redirected: "physical security" becomes each remote worker's home setup (covered by A.6.7 Remote working) plus whatever your cloud/hosting provider's physical controls documentation covers. Don't delete the theme; reframe it around what you actually control.
- Wherever this file says "confirm the landlord/provider meets your minimum bar," that confirmation itself is the evidence an assessor wants: a one-line email confirming a co-working space has 24/7 monitored entry is a legitimate, sufficient artefact; you don't need to inspect their premises yourself.
- Cabling security (A.7.12) genuinely doesn't apply in the traditional sense to a fully wireless, cloud-hosted operation. Say so explicitly in your Statement of Applicability rather than stretching the control to fit.
