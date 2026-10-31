# Neighborhood Membership

## 1. Purpose

SOLACE Network organizes participating households into geographically defined neighborhoods.

Neighborhoods provide a local community structure through which households can communicate, cooperate, share resources, and eventually operate independent network infrastructure.

This document describes how neighborhoods are created, how households become members, and how geographic membership is established.

**Status:** Working architecture. This document records established design principles and identifies procedures requiring further development.

Phase 1 will use the centralized SOLACE Server. Offline neighborhood operation, decentralized identity verification, and mesh networking belong to later development phases.

## 2. Neighborhood Identity (NID)

Every SOLACE neighborhood receives a unique Neighborhood Identifier (NID).

The NID identifies the neighborhood independently of its name, Captain, participating households, or infrastructure.

The following principles apply:

- A neighborhood receives its NID when created.
- The NID remains associated with that neighborhood throughout its lifetime.
- A neighborhood has a defined geographic boundary.
- A household belongs to one NID at a time.
- Households may eventually change their neighborhood affiliation without changing their HID.
- Neighborhoods may contain different numbers of households.

Neighborhood membership is based on households rather than individual members or devices.

## 3. Geographic Boundaries

### 3.1 Geographic organization

SOLACE neighborhoods are intended to represent actual geographic communities, such as a street, a cluster of nearby homes, or an apartment complex.

Neighborhood boundaries establish the geographic area eligible for household membership.

Boundaries are not intended to follow arbitrary political or administrative divisions.

### 3.2 Boundary creation

The proposed Phase 1 creation process uses an interactive Google Map.

A member establishing a new neighborhood will:

1. Identify their geographic location.
2. Draw a boundary around the proposed neighborhood.
3. Review the area covered by that boundary.
4. Submit the neighborhood for creation.

The server must check the proposed boundary against existing neighborhoods.

**New neighborhoods must not overlap existing neighborhood boundaries.**

### 3.3 Boundary permanence

The current design calls for neighborhood boundaries to remain fixed after creation.

Subsequent households join existing neighborhoods rather than modifying their boundaries.

Procedures for correcting mistaken boundaries, resolving disputes, or reorganizing neighborhoods have not yet been defined.

### 3.4 Neighborhood size

Earlier planning proposed approximately 30 physical households as a reasonable initial neighborhood size.

This is a planning guideline, not a permanent population limit.

A neighborhood may grow beyond 30 participating households, potentially exceeding 100, as additional eligible households register.

The precise geographic size restrictions and validation rules remain to be determined.

## 4. Creating a Neighborhood

### 4.1 Initial creator

The first member establishing a neighborhood becomes its initial Neighborhood Captain.

That member also creates or associates their own household with the neighborhood.

Neighborhood creation establishes an NID, but does not automatically establish HIDs for every physical residence inside the boundary.

### 4.2 Captain responsibilities

The Captain serves as the neighborhood's initial organizer and primary contact.

Potential responsibilities include:

- Helping neighbors understand SOLACE.
- Encouraging household registration.
- Distributing invitations.
- Coordinating initial neighborhood activities.
- Performing authorized neighborhood administrative tasks.

The Captain does not personally own the neighborhood or its member households.

### 4.3 Limits on Captain authority

A Captain cannot create household memberships on behalf of other residents simply because their addresses fall within the neighborhood.

Each household must establish its own HID through an authorized registration process.

The Captain's approval is not required for an eligible, geographically verified household to join.

Captain succession, removal, and governance authority are addressed separately in `IDENTITY_AND_GOVERNANCE.md`.

## 5. Joining an Existing Neighborhood

### 5.1 Geographic eligibility

A household located inside an existing neighborhood boundary may join that neighborhood.

The intended process is:

1. A resident registers or signs in.
2. The resident establishes a household or joins an existing HID.
3. The system determines the household's geographic location.
4. The server identifies the neighborhood containing that location.
5. The household joins the corresponding NID once its eligibility is verified.

Membership should not depend on discretionary Captain approval when geographic eligibility has been established.

### 5.2 Household membership

The HID is the neighborhood membership unit.

Individual members belong to households through their MIDs, and the household establishes their neighborhood affiliation.

The Head of Household manages membership within the HID, subject to applicable account permissions.

Neighborhood Captains do not automatically acquire administrative authority over the MIDs belonging to participating households.

### 5.3 One neighborhood per household

A household has one primary NID affiliation at a time.

Membership in other neighborhoods, temporary guest access, and participation in inter-neighborhood activities must be distinguished from primary neighborhood membership.

Guest access to another neighborhood does not automatically establish membership in that NID.

## 6. Household Location Verification

### 6.1 Initial verification

Earlier planning proposed using browser geolocation to establish that a household is within the relevant neighborhood boundary.

Location verification may occur during registration or when establishing a household's neighborhood membership.

Once verified, the household's geographic eligibility can be recorded without requiring continuous location tracking.

### 6.2 Verification limitations

A device's location is not necessarily proof that its user resides at that address.

Browser geolocation establishes a device's reported position, subject to accuracy and possible manipulation.

Consequently, the system must distinguish between:

- A household's declared residential address.
- A device's reported geographic location.
- The household's verified or approved membership status.

The exact evidence required to establish residence remains unresolved.

### 6.3 Privacy

SOLACE should avoid unnecessary collection and continuous monitoring of household locations.

Geographic verification should collect only the information reasonably necessary to establish membership eligibility.

Policies for retaining coordinates, protecting residential addresses, and controlling who may view household locations require further specification.

## 7. Household Invitations and Recruitment

Neighborhood growth depends on existing members inviting nearby households to participate.

Any participating household may invite neighbors. Recruitment is not exclusively a Captain responsibility.

Captains should be encouraged to invite neighbors during the initial neighborhood creation process.

### 7.1 Invitation methods

Previously discussed invitation methods include:

- Email invitations.
- Shareable invitation URLs.
- QR codes.
- Printable flyers or handouts.

Invitations should make participation easy for people with different levels of technical experience.

### 7.2 Invitation messaging

Initial messaging should explain SOLACE in practical, accessible terms.

Potential themes include local cooperation, neighborhood communication, resource sharing, community independence, and emergency preparedness.

The invitation can provide a short introduction with a link to more detailed information.

Different invitation messages may eventually be tested to understand which best communicate the network's purpose.

### 7.3 Invitations are not memberships

Receiving an invitation does not automatically create an MID, HID, or NID membership.

The recipient must complete the appropriate registration and eligibility process.

An invitation does not override geographic membership requirements.

## 8. Neighborhood Participation

A neighborhood can begin operating with its first registered household.

There is no minimum household population required before participating members may use available Phase 1 features.

Potential neighborhood applications include:

- Local messaging and announcements.
- Neighborhood calendars and events.
- Polls and community coordination.
- Requests for assistance.
- Tool and resource sharing.
- Community classifieds.
- Emergency preparedness planning.

Individual application features will be specified separately and introduced incrementally.

A household's voting rights and neighborhood participation must remain independent of how many members or devices it contains.

## 9. Moving Between Neighborhoods

Households may eventually change their NID affiliation while retaining their permanent HID.

Possible reasons include relocation, correction of an incorrect assignment, or an approved change in neighborhood membership.

A transfer should not require deleting the household or creating new MIDs for its members.

The following details remain undecided:

- How transfers are requested and authorized.
- Whether location must be verified again.
- How prior neighborhood membership history is retained.
- How existing neighborhood-specific content and permissions are handled.
- Whether any waiting period applies to governance participation after a transfer.

A household should not hold simultaneous primary memberships in multiple NIDs.

## 10. Membership Costs and Accessibility

SOLACE neighborhood membership is intended to be free.

There are no mandatory neighborhood dues, subscription fees, or paywalls required simply to join and participate.

Neighborhoods may independently organize voluntary funding for local activities or infrastructure.

Voluntary financial contributions must not increase a household's voting weight.

The broader SOLACE vision supports participation through compatible hardware from multiple vendors, but ownership of specialized networking equipment is not a prerequisite for initial Phase 1 registration.

## 11. Implementation Considerations

The existing `solace-main` Laravel prototype provides an initial foundation for neighborhood and household registration.

Previously reviewed components include:

- A `neighborhoods` table containing NIDs, neighborhood labels, geographic geometry, and Captain references.
- A `houses` table containing HIDs, addresses, coordinates, and neighborhood associations.
- A household-member relationship table.
- A Livewire registration wizard.
- Google Maps integration used in the registration interface.

These are prototype components, not confirmation that the complete neighborhood creation and membership workflows are implemented.

### Phase 1 priorities

The initial implementation should focus on:

1. Creating persistent neighborhood records.
2. Capturing and validating geographic boundaries.
3. Preventing overlapping neighborhoods.
4. Associating registered households with the appropriate NID.
5. Establishing the initial Captain role.
6. Verifying household eligibility.
7. Enforcing appropriate permissions for household and neighborhood operations.

Invitation and recruitment features may be developed incrementally.

## 12. Unresolved Decisions

The following questions require further discussion:

### Geographic boundaries
- What exact size restrictions should apply to new neighborhoods?
- How should invalid, excessively large, or self-intersecting boundaries be handled?
- What happens to an address located precisely on a boundary?
- How are mapping errors and disputed boundaries corrected?
- How should multi-unit buildings and apartment complexes be represented?

### Membership verification
- What evidence is sufficient to verify residence?
- What happens when a user denies browser location permission?
- How are households without accurate GPS or browser geolocation supported?
- Who may review or challenge a household's verified status?
- What safeguards prevent duplicate or fraudulent household registrations?

### Neighborhood administration
- What actions can a Captain perform in Phase 1?
- How are abandoned or incorrectly created neighborhoods handled?
- How can households appeal a membership or boundary decision?

### Transfers and access
- How does a household move between NIDs?
- What information remains available after leaving a neighborhood?
- How should temporary guests and cross-neighborhood participation work?

### Invitations
- Should invitations contain neighborhood-specific information?
- Should invitation links expire?
- What invitation statistics, if any, should be collected?

These questions should be resolved through focused policy and implementation discussions rather than assumed to have settled answers.

## 13. Related Documentation

- [Identity and Governance](IDENTITY_AND_GOVERNANCE.md) — MID, HID, FID, NID, leadership, and voting principles.
- [Network Overview](NETWORK_OVERVIEW.md) — Overall architecture and development phases.
- [Vision](VISION.md) — Community mission and guiding principles.
- [Roadmap](ROADMAP.md) — Development priorities.
- [Hardware](HARDWARE.md) — Future neighborhood infrastructure.
- [Parking Lot](PARKING_LOT.md) — Deferred ideas and research topics.
