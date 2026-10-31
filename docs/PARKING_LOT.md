# PARKING LOT: The Place to Park Things

New ideas that don't belong in technical specifications or the roadmap can be documented here so they aren't forgotten.

**Items in this document have no assigned priority, development schedule, or release milestone.**

They represent features, enhancements, experiments, and possibilities discussed during SOLACE Network planning.

Some may eventually move into a technical specification or roadmap. Others may never be implemented.

An idea appearing here does not mean it has been approved.

---

## 1. Network Communication and Messaging

### 1.1 Delay-Tolerant Messaging

Allow SOLACE messages to travel through the network even when no continuous connection exists between sender and recipient.

Potential capabilities include:

- Store-and-forward message delivery.
- Persistent outbound and inbound message queues.
- Encrypted message bundles.
- Delivery acknowledgments.
- Message expiration.
- Duplicate detection.
- Opportunistic routing between disconnected networks.

Distributed message delivery involves substantial technical challenges, and detailed design has been explicitly deferred.

See [Network Overview](NETWORK_OVERVIEW.md).

### 1.2 Mobile Devices as Data Mules

A SOLACE application running on a mobile device could carry encrypted messages between disconnected neighborhoods.

For example:

1. A phone encounters one neighborhood's mesh network.
2. The application receives permitted message bundles.
3. The phone travels to another neighborhood.
4. The application transfers appropriate messages to the second network.

The user might not need to interact with the application during each exchange.

Potential challenges include mobile operating-system restrictions, battery consumption, storage limits, authentication, message forwarding policies, and security.

Guest access to neighborhood infrastructure could make this capability particularly useful.

### 1.3 Radio Messaging Integration

Investigate interoperability with independent radio communication systems, including Meshtastic, MeshCore, and MeshOS-related implementations.

Possible features include:

- Associating radio device identifiers with SOLACE member identities.
- Low-bandwidth text messaging.
- Local message exchange when internet access is unavailable.
- Bridging messages between radio networks and other SOLACE communication services.

Different radio systems may have incompatible protocols and capabilities.

No integration approach has been selected.

### 1.4 Cross-Neighborhood Message Relays

Explore ways for neighborhoods to exchange information through volunteer-operated gateways, intermediary SHDs, or other authorized relay systems.

Potential features include configurable routing permissions, resource limits, and alternate paths during outages.

The basic direction is covered by the network architecture. Specific relay mechanisms remain future work.

### 1.5 Voice and Video Communication

Earlier SOLACE concepts included:

- Voice calling.
- Video calling.
- Group conversations.
- Other real-time communication services.

These capabilities may eventually complement text messaging.

Their practical requirements, particularly bandwidth and connectivity, have not been evaluated.

---

## 2. Network Discovery, Mapping, and Monitoring

### 2.1 Distributed Network Health Monitoring

Expand the proposed SHD status service into a distributed system that can exchange authenticated connectivity and health observations.

Potential capabilities include regional summaries, historical reliability information, and status reporting from independently operated gateways.

This is a long-term extension of the Network Presence architecture rather than a Phase 1 requirement.

### 2.2 Historical Network Coverage Analysis

Provide views showing how verified SOLACE connectivity changes over time.

Potential applications include:

- Identifying recurring outages.
- Comparing connection reliability.
- Measuring network growth.
- Studying seasonal connectivity changes.
- Understanding the effects of new infrastructure.

Coverage information should be based on confirmed measurements rather than proposed or speculative installations.

### 2.3 Network Status and Signal Indicators

Explore improved visual indicators showing whether a SOLACE application has access to:

- The central service.
- Local household services.
- A neighborhood mesh.
- Authorized guest connectivity.
- Other reachable network services.

A cellphone-style signal indicator was discussed as a simple interface.

The detailed measurements and display conventions remain undecided.

### 2.4 Gateway and Connectivity Discovery

Explore discovery mechanisms allowing devices to identify available SOLACE services and compatible gateways.

Future implementations may need to operate without a Foundation-operated server.

Potential considerations include service advertising, authentication, reachability, and choosing between multiple available paths.

---

## 3. Identity, Authentication, and Account Recovery

### 3.1 Portable Cryptographic Identity

Investigate user-controlled cryptographic credentials capable of authenticating members, households, and neighborhoods without relying permanently on a centralized server.

Topics discussed include:

- Device-generated public/private key pairs.
- Multiple authorized keys per identity.
- Key replacement and revocation.
- Signed administrative delegations.
- Independent identity verification.

These ideas are already described at a high level in [Identity and Governance](IDENTITY_AND_GOVERNANCE.md).

Implementation details remain undecided.

### 3.2 Printable Identity Recovery Cards

Explore an offline identity backup or recovery mechanism for nontechnical participants.

Earlier concepts included:

- Downloadable encrypted backup files.
- Printable SOLACE Identity Recovery Cards.
- QR codes containing appropriate recovery information.
- Human-readable identifying information or recovery codes.
- Offline backups stored on removable media.

The goal would be to simplify credential recovery while avoiding reliance on a permanently available central server.

Recovery mechanisms would require careful security design.

### 3.3 Optional Biometric Authentication

Explore fingerprint or facial authentication as an optional way to unlock locally stored SOLACE credentials.

The initial concept favors using established device authentication capabilities rather than collecting biometric information centrally.

A conventional password, PIN, security key, or comparable alternative should remain available.

### 3.4 Wearable-Assisted Authentication

Investigate whether a trusted smartwatch, ring, or similar wearable could help maintain a session while its owner is nearby.

Potential behavior includes:

- Strong authentication when opening an application.
- Continued access while an authenticated wearable remains nearby.
- Locking or requiring additional authentication when the wearable is absent.
- Reauthentication before sensitive account or governance operations.

Proximity would supplement authentication rather than replace it.

### 3.5 Context-Aware Session Security

Explore additional signals, such as recognized household networks or trusted device proximity, to assist with security decisions.

Possible applications include adaptive authentication and session management.

Location, network familiarity, or nearby hardware should not be treated as conclusive proof of identity.

### 3.6 Decentralized Governance Records

Investigate methods for independently verifying household voting and neighborhood decisions.

Potential capabilities include signed proposals, verifiable eligibility, delegation records, replay protection, and auditability.

A blockchain was mentioned as a possibility in early planning but has not been adopted as a requirement.

Governance procedures and authority rules belong in the identity specification.

---

## 4. Local Computing and Household Services

### 4.1 Optional Nextcloud Integration

Investigate Nextcloud as an optional service on an SHD.

Possible uses include:

- Household file storage.
- Shared documents.
- Calendars.
- Contacts.
- Synchronization between personal devices and household storage.

Nextcloud should not be a mandatory dependency for all SOLACE applications.

### 4.2 Offline Knowledge Libraries

Support downloadable and locally accessible reference materials.

Kiwix and offline Wikipedia were discussed as potential components.

Possible enhancements include:

- Curated knowledge collections.
- Household-specific reference libraries.
- Educational materials.
- Repair and maintenance instructions.
- Community-contributed documentation.

An offline knowledge library could remain useful even when internet connectivity is unavailable.

### 4.3 Household Shared Storage

Explore a shared folder or local file-sharing service accessible to authorized household members.

Potential features include permissions, synchronization, backups, and optional sharing with trusted neighboring households.

### 4.4 Optional Local AI Server

A household or neighborhood could operate a local language-model server.

Possible uses include:

- Research assistance.
- Household troubleshooting.
- Document analysis.
- Calendar and project coordination.
- Educational assistance.
- Collaborative problem-solving.

The original concept favored a more powerful optional computer rather than requiring every SHD to run an AI model.

### 4.5 AI Resource Prioritization

A shared AI server could prioritize requests according to purpose and authorization.

For example, technical troubleshooting of a neighborhood power system might take precedence over recreational requests.

Potential controls include:

- Permissions associated with members or households.
- Resource quotas.
- Request prioritization.
- Limits on concurrent workloads.
- Fair access between participating households.

This remains a future service-design concept.

### 4.6 Locally Stored AI Conversations

Explore a browser-based AI interface in which conversation histories remain on the user's local device while the model runs on a separate household or neighborhood server.

The concept was inspired by interfaces that keep conversation records locally.

Potential considerations include shared-document access, client-side storage, privacy, and authorization.

---

## 5. Community and Neighborhood Applications

### 5.1 Community Forums and Discussion

Future neighborhood applications may provide discussion forums, group conversations, and other ways for neighbors to communicate.

The original SOLACE concept described this as part of "social media with a purpose."

### 5.2 Local Classifieds and Exchanges

Explore neighborhood listings for:

- Items for sale.
- Items offered free.
- Services.
- Barter.
- Community exchanges.
- Requests for equipment or assistance.

The purpose would be to encourage practical local cooperation.

### 5.3 Shared Tools and Resources

Investigate community inventories of tools, equipment, and other shared resources.

Possible features include reservations, availability, lending records, and permissions.

### 5.4 Neighborhood Calendars

Potential applications include shared calendars for community events, volunteer projects, and neighborhood activities.

Calendar functionality may eventually integrate with household or local AI services.

### 5.5 Community Project Coordination

Explore tools for organizing collaborative projects.

Potential uses include gardening projects, neighborhood improvements, volunteer work, and community preparedness.

### 5.6 Neighborhood Security and Alerts

An early SOLACE application concept included:

- Security cameras.
- Sensors.
- Neighborhood alerts.
- Weather alerts.
- Public safety information.
- Local incident reporting.

These ideas require careful attention to privacy, data quality, authorization, and the potential for misuse.

No particular security or surveillance feature has been approved.

### 5.7 Bookkeeping and Accounting

Earlier planning included optional bookkeeping and accounting tools.

Potential uses might include household projects, shared community resources, or neighborhood organizations.

Detailed requirements have not been established.

### 5.8 Payments and Financial Services

An early plug-in concept included electronic payments and community financial services.

These ideas are not part of the current development scope.

Any future implementation would require substantial consideration of security, regulatory obligations, and financial risk.

---

## 6. Education and Knowledge Sharing

### 6.1 Home Education Resources

Earlier SOLACE proposals included resources for homeschooling and family education.

Potential capabilities include:

- Educational reference collections.
- Learning materials.
- Community-shared instructional resources.
- Connections between participating parents.
- Collaborative learning activities.

The exact relationship to future SOLACE education applications remains to be determined.

### 6.2 Practical Skills Library

Explore a collection of instructional materials supporting the "Back to Basics, Made Easier" philosophy.

Possible subjects include:

- Gardening.
- Food preservation.
- Home maintenance.
- Repair and reuse.
- Practical science.
- Community preparedness.

Materials could be available online or stored locally for offline use.

### 6.3 Community-Contributed Learning Materials

Allow participants to contribute approved instructional content or share useful knowledge with other households.

Potential requirements include moderation, provenance, permissions, and appropriate licensing.

### 6.4 Local Educational Collections

A neighborhood could maintain its own curated collection of learning materials.

This might supplement individually downloaded resources and remain accessible through local household or neighborhood infrastructure.

---

## 7. Household and Device Interfaces

### 7.1 Low-Power Status Displays

Explore a small e-ink display showing household or network information without requiring a full-size monitor.

Possible information includes:

- Connection status.
- Battery level.
- Local network availability.
- Device health.
- Service notifications.

Related hardware concepts are described in [Hardware](HARDWARE.md).

### 7.2 Hybrid Display Concepts

An earlier idea involved combining the benefits of conventional LED displays and e-ink technology.

The goal would be to reduce power consumption while maintaining a useful interactive display.

This is an exploratory interface and hardware concept, not a baseline SHD requirement.

### 7.3 Enhanced SOLACE Status Symbol

Investigate additional uses of the illuminated SOLACE symbol as a device-status interface.

The earlier proposal used green, yellow, and red lighting to communicate different connectivity or power conditions.

Detailed status conventions remain undecided.

---

## 8. Software Distribution and Ecosystem

### 8.1 Optional SOLACE Hardware Kits

Explore the possibility of assembling complete reference kits from existing commercial components.

Such kits might contain a computer, router, antenna, and battery backup.

They would remain optional alternatives to independently assembled compatible equipment.

### 8.2 Compatible Device Catalog

Publish tested lists of computers, routers, radios, batteries, and related equipment.

Potential information includes compatibility status, known limitations, power requirements, and installation instructions.

This would support the vendor-neutral hardware philosophy.

### 8.3 Additional Application Modules

The original SOLACE concept included a broad collection of optional plug-ins.

Potential modules beyond the initial applications could include research tools, accounting, security, community marketplaces, and additional communication features.

These should be considered individually rather than treated as a fixed development commitment.

### 8.4 Additional Application Integration

Explore ways for independently developed applications to connect with SOLACE services through documented APIs and shared identity mechanisms.

The objective is to support a modular ecosystem without requiring all applications to share one codebase.

Specific extension mechanisms remain undecided.

---

## 9. Future Research and Scientific Collaboration Features

Scientific research subjects are documented separately in [SOLACE Scientific Research Topics](SOLACE_SCIENTIFIC_RESEARCH_TOPICS.md).

However, the software infrastructure supporting community research may eventually require additional features.

Potential capabilities include:

- Research project registration and management.
- Structured observation forms.
- Dataset publication and versioning.
- Community collaboration tools.
- Research participant permissions.
- Data export and analysis.
- Research review and quality-control workflows.

These are possible software capabilities, not currently scheduled development requirements.

The research topics themselves, including alternative energy, gardening, fungi, and environmental monitoring, belong in the separate scientific research document.

---

## 10. Historical Concepts Worth Preserving

A few ideas from the original SOLACE project may not fit neatly into the current architecture but remain worth recording.

### 10.1 Virtual Overlay and Independent Networking

Earlier descriptions characterized SOLACE as both an internet-based overlay and a separate communications network capable of operating without conventional internet infrastructure.

The modern four-phase architecture expresses this direction more precisely.

The historical concept remains part of SOLACE's design background.

### 10.2 A Modular Framework for Daily Life

Early SOLACE planning envisioned a very broad application ecosystem involving communication, education, gardening, household services, security, accounting, finance, and research.

The current architecture favors developing smaller independent applications rather than attempting to deliver the entire ecosystem at once.

### 10.3 Community-Controlled Infrastructure

The project has consistently explored the possibility of households and neighborhoods operating their own equipment and services.

This remains a foundational long-term direction, even though many particular implementations are undecided.

---

## 11. Moving Ideas Out of the Parking Lot

Ideas in this document have no implied priority.

Before an item becomes planned development work, it should receive further review to establish:

1. The problem it addresses.
2. Who would benefit from it.
3. Whether it fits SOLACE's mission.
4. Its relationship to existing architecture.
5. Technical feasibility and dependencies.
6. Security, privacy, and maintenance implications.
7. Whether it belongs in an existing application or a separate project.

Once approved for development, the item can move into an appropriate technical specification and eventually into a roadmap milestone.

An idea may also remain here indefinitely or be explicitly rejected.

## 12. Related Documentation

- [Vision](VISION.md) — Long-term mission and purpose.
- [Network Overview](NETWORK_OVERVIEW.md) — Four-phase architecture and connectivity.
- [Identity and Governance](IDENTITY_AND_GOVERNANCE.md) — Identity, administrative authority, and household voting.
- [Neighborhood Membership](NEIGHBORHOOD_MEMBERSHIP.md) — Neighborhood creation and membership.
- [Hardware](HARDWARE.md) — Practical hardware architecture and compatibility.
- [Scientific Research Topics](SOLACE_SCIENTIFIC_RESEARCH_TOPICS.md) — Scientific questions and experimental research.
- [Roadmap](ROADMAP.md) — Approved development priorities and milestones.
- [Branding and Marketing](BRANDING_AND_MARKETING.md) — Brand identity and promotional ideas.