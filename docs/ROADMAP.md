# SOLACE Network Roadmap

## 1. Overview

SOLACE Network is being developed incrementally, beginning with centrally hosted applications and eventually evolving toward independent, community-operated networks.

The project is organized into four major development phases.

**Our immediate priority is Phase 1.** Later phases describe the long-term direction but are not currently scheduled for implementation.

Each phase should deliver useful capabilities while establishing a foundation for future development.

For the broader mission and long-term aspirations, see [Vision](VISION.md).

For network architecture and the relationship between phases, see [Network Overview](NETWORK_OVERVIEW.md).

## 2. Development Phases

| Phase | Name | High-Level Goal | Status |
|---|---|---|---|
| 1 | Centralized | Establish the central SOLACE Server, membership system, and initial applications | Current focus |
| 2 | Household Computing | Introduce local SOLACE Home Devices and household-hosted applications and services | Future |
| 3 | Hybrid Mesh Networking | Enable direct communication between participating households through neighborhood networking infrastructure | Future |
| 4 | Independent Decentralized Network | Enable independent communication and cooperation without requiring the central SOLACE Server | Future |

---

## 3. Phase 1 — Centralized

**Status: Planning and initial development**

### Primary Goal

Establish a functional SOLACE Network foundation using a centrally hosted web platform.

Participants should be able to create accounts, establish households, join neighborhoods, and begin using practical applications without purchasing or installing specialized hardware.

The initial system will use conventional internet infrastructure and centrally managed services.

### 3.1 Core Server and Infrastructure

Establish the central SOLACE Server as the initial home for membership services, applications, and shared APIs.

Initial development areas:

- Laravel-based server application.
- Database infrastructure.
- Account authentication and management.
- Authorization and role management.
- Application and service APIs.
- Development, testing, and deployment environments.
- Documentation and basic administrative capabilities.

The existing `solace-main` Laravel prototype provides historical code and design references for this work.

The Phase 1 implementation plan should be developed after reviewing the current prototype and identifying reusable components.

### 3.2 Identity and Membership

Establish the core identity structure:

- Member identifiers (MID).
- Household identifiers (HID).
- Family identifiers (FID), for guardian–minor relationships.
- Neighborhood identifiers (NID).

Initial functionality should support:

- Adult member registration and account management.
- Household creation and membership.
- Head of Household administration.
- Guardian-managed accounts for minors.
- Family relationships linking minors to authorized adult guardians.
- Neighborhood creation and membership.
- Initial Neighborhood Captain assignment.
- Appropriate account, household, and neighborhood permissions.

Minors cannot independently create accounts. They must be added by authorized adult guardians to an existing household and family unit.

Detailed policies are documented in [Identity and Governance](IDENTITY_AND_GOVERNANCE.md).

### 3.3 Neighborhood Registration

Develop the initial neighborhood creation and membership workflows.

Proposed capabilities include:

- Creating geographically defined neighborhoods.
- Defining neighborhood boundaries through an interactive map.
- Preventing overlapping neighborhood boundaries.
- Associating households with the appropriate neighborhood.
- Establishing geographic eligibility for membership.
- Supporting household registration within an existing neighborhood.
- Providing initial neighborhood administrative functionality.

Neighborhoods may begin with a single participating household and grow as additional households join.

Invitation and recruitment capabilities may be introduced incrementally.

See [Neighborhood Membership](NEIGHBORHOOD_MEMBERSHIP.md).

### 3.4 Initial Applications

Begin developing practical applications that give people reasons to participate in SOLACE.

The initial application effort includes **SOLACE Garden**, with its own repository and technical specification.

Applications should be modular where practical and use shared SOLACE services when appropriate.

Phase 1 applications may operate through a browser or Progressive Web App and use centralized services for shared data.

The specific order, scope, and release requirements of additional applications have not yet been determined.

Detailed implementation plans belong in each application's repository.

### 3.5 User Experience and Accessibility

The initial platform should be approachable for participants who are not technically experienced.

Development considerations include:

- Clear registration and onboarding workflows.
- Responsive interfaces for desktop and mobile devices.
- Understandable household and neighborhood management.
- Accessible navigation and terminology.
- Basic account recovery and support information.
- Clear distinction between available and planned capabilities.

The system should not require participants to understand SOLACE's eventual networking architecture.

### 3.6 Documentation and Project Organization

Establish and maintain project documentation before and during implementation.

Current documentation includes:

- [Vision](VISION.md)
- [Network Overview](NETWORK_OVERVIEW.md)
- [Identity and Governance](IDENTITY_AND_GOVERNANCE.md)
- [Neighborhood Membership](NEIGHBORHOOD_MEMBERSHIP.md)
- [Hardware](HARDWARE.md)
- [Branding and Marketing](BRANDING_AND_MARKETING.md)
- [Scientific Research Topics](SOLACE_SCIENTIFIC_RESEARCH_TOPICS.md)
- [Parking Lot](PARKING_LOT.md)

Organization-level documents describe SOLACE as a whole.

Detailed application specifications, implementation tasks, and release information should remain in their respective repositories.

### 3.7 Initial Phase 1 Milestones

The following milestones are proposed for organizing development. Their sequence and scope may change after reviewing the existing codebase.

- [ ] **Milestone 1 — Core platform assessment:** Review `solace-main`, identify reusable components, and define the initial Phase 1 implementation approach.
- [ ] **Milestone 2 — Membership foundation:** Implement and validate member, household, family, and neighborhood data relationships.
- [ ] **Milestone 3 — Registration and onboarding:** Complete adult registration, household creation, guardian-managed minor accounts, and neighborhood registration workflows.
- [ ] **Milestone 4 — Membership administration:** Implement essential household and neighborhood roles, permissions, and administrative operations.
- [ ] **Milestone 5 — Initial application integration:** Establish the shared services needed to connect the first SOLACE applications to the platform.
- [ ] **Milestone 6 — Initial public release:** Test and deploy an initial usable version of the platform with its selected application capabilities.

These are planning milestones, not finalized release commitments.

### 3.8 Phase 1 Completion Criteria

Before declaring Phase 1 complete, the project should have:

- A deployed and operational central SOLACE platform.
- Working member registration and authentication.
- Functional household and neighborhood creation and membership.
- Basic support for guardian–minor family relationships.
- Appropriate account and administrative permissions.
- At least one useful application accessible to participants.
- Tested core workflows and sufficient documentation to operate and maintain the platform.

Phase 1 does not require SOLACE Home Devices, neighborhood mesh equipment, decentralized messaging, or independent network infrastructure.

---

## 4. Phase 2 — Household Computing

**Status: Future — Not Yet Scheduled**

### High-Level Goal

Introduce SOLACE Home Devices, allowing participating households to operate local applications, databases, storage, and other services.

Personal devices may access household-hosted services, while the central SOLACE Server continues supporting communication between households.

This phase will focus on local computing, compatible hardware, installation and maintenance, and synchronization between local and central services.

Detailed milestones will be developed when Phase 1 is sufficiently mature.

See [Hardware](HARDWARE.md) and [Network Overview](NETWORK_OVERVIEW.md).

---

## 5. Phase 3 — Hybrid Mesh Networking

**Status: Future — Not Yet Scheduled**

### High-Level Goal

Enable participating households to communicate directly through neighborhood-operated networking infrastructure.

The architecture will combine direct household connectivity with the existing central SOLACE services where appropriate.

This phase introduces practical mesh-network interoperability and shared connectivity between participating households.

Detailed milestones will be developed after the foundational household-computing capabilities are established.

See [Network Overview](NETWORK_OVERVIEW.md).

---

## 6. Phase 4 — Independent Decentralized Network

**Status: Future — Not Yet Scheduled**

### High-Level Goal

Enable SOLACE households and neighborhoods to communicate and cooperate without requiring the central SOLACE Server.

Foundation-operated services may remain available as optional infrastructure alongside independently operated gateways and local networks.

The mature network should support independent operation while allowing communities to participate in a broader interoperable system.

Detailed milestones will be developed after earlier phases provide operational experience and validated infrastructure.

See [Vision](VISION.md) and [Network Overview](NETWORK_OVERVIEW.md).

---

## 7. Roadmap Principles

The following principles guide development:

1. **Phase 1 comes first.** Deliver a useful centralized platform before implementing household networking hardware.
2. **Build incrementally.** Each development milestone should produce something testable and useful.
3. **Preserve future options.** Avoid unnecessary architectural choices that would prevent future local-first or decentralized operation.
4. **Separate goals from specifications.** The roadmap defines intended outcomes; technical specifications define detailed requirements.
5. **Keep applications modular.** Application-specific work belongs in its own repository.
6. **Avoid premature commitments.** Features without approved scope or dependencies remain outside scheduled milestones.
7. **Review existing work.** Reuse useful lessons and components from earlier SOLACE prototypes rather than automatically starting over.

## 8. Future Ideas and Research

SOLACE has accumulated many proposed capabilities that are not currently part of the development schedule.

These are documented in:

- [Parking Lot](PARKING_LOT.md) — Deferred software, network, and service ideas.
- [Scientific Research Topics](SOLACE_SCIENTIFIC_RESEARCH_TOPICS.md) — Experimental and community research subjects.

Being documented does not imply a commitment to implementation.

---

*This roadmap is a working planning document. Priorities and milestones may change as development progresses.*