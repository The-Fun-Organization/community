# Landos: A Sovereign Land Ownership Protocol

**Version:** 0.1.0  
**Status:** Draft  
**Date:** 2026-06-01  
**Token:** Landos Equity Token (LOS)  

---

> *"Land locked from its rightful owners is poverty by design. This chain breaks that lock — for everyone, forever, without permission."*
>
> — Landos Genesis Block

---

## Abstract

Landos is a sovereign, decentralized blockchain protocol for land ownership registration and verification. It provides a permanent, incorruptible, cryptographically verifiable record of land ownership that no government, institution, or individual controls.

The protocol is designed for the hundreds of millions of people worldwide whose land ownership exists only in community memory — people who have occupied land for generations but have no formal record that a legal or financial system would recognize. For these people, the absence of a formal record is not merely a bureaucratic inconvenience. It is one of the primary mechanisms that traps them in poverty.

Landos applies two proven frameworks to this problem. The first is Bitcoin's sovereignty principle: a distributed, decentralized ledger that requires no institutional trust and cannot be corrupted by any single actor. The second is Hernando de Soto's dead capital thesis: that formalizing land ownership transforms economically inert assets into live capital, unlocking credit, investment, and intergenerational wealth transfer.

Landos brings both frameworks together. The result is a land ownership system that is permanent, accessible, community-validated, privacy-preserving, and economically meaningful — built specifically for the people who have never had one.

---

## 1. Introduction

### 1.1 The Problem

Land ownership today is entirely dependent on governments and institutions. Registries are siloed, incompatible, and inconsistent across countries and regions. Records are vulnerable to corruption — officials can alter, delete, or forge them. In many parts of the world, records barely exist at all.

These are not edge cases. They are the everyday reality for hundreds of millions of people — farmers, indigenous communities, families with no legal recourse when someone more powerful decides to take what is theirs.

The core problem is structural: **land ownership is controlled by whoever controls the registry. And registries can be corrupted.**

The consequences extend beyond insecurity. In 2000, economist Hernando de Soto estimated that the world's poor hold approximately $9.3 trillion in "dead capital" — land and assets that have real value but cannot be used economically because they lack formal recognition [1]. This land cannot be used as loan collateral. It cannot attract investment. It cannot be formally sold or transferred. It simply exists, valuable but locked.

**The compound problem: land is both insecure and economically dead for the people who need it most.**

### 1.2 The Opportunity

Bitcoin proved in 2009 that a monetary record could exist outside of government and institutional control — permanent, incorruptible, verifiable by anyone [2]. Satoshi Nakamoto's insight was that distributed consensus among independent participants could replace institutional trust entirely.

De Soto proved through decades of fieldwork that the act of formalizing ownership — creating a recognized, legible record — converts dead capital into live capital. The record itself is the economic transformation [1].

Landos applies both insights to land. A sovereign, decentralized blockchain makes it possible for people to register land ownership without institutional permission. Community validation — encoding the social knowledge that communities already hold — makes those registrations verifiable and trustworthy. And the resulting record, permanently anchored to Bitcoin and accessible to global capital markets, transforms dead land into live economic capital.

### 1.3 Design Philosophy

Landos is designed around four philosophical commitments:

**Sovereignty.** No government, corporation, or individual controls the Landos protocol. Like Bitcoin, it earns legitimacy through adoption and through the undeniable fact of records that work — not through institutional permission.

**Community.** Land is not purely an individual thing. A person owns land within a community. Their neighbors know them. The community has memory that no individual has. Landos encodes that social reality into the protocol as a foundational design principle.

**Accessibility.** The people Landos exists to serve — the farmer in West Africa, the family in an informal settlement, the indigenous community whose territory has never been formally mapped — must be able to use it. Cost, technical complexity, and connectivity constraints cannot be barriers to entry.

**Permanence.** A land record is only valuable if it persists. Landos records are designed to survive institutional failure, political change, and technological disruption — anchored to Bitcoin, the most durable digital record system ever created.

---

## 2. Prior Art and Failures

### 2.1 Previous Blockchain Land Projects

Every blockchain land registration project to date has failed or delivered marginal impact. Understanding why is essential to understanding the Landos design.

**Honduras / Factom (2015):** The government of Honduras partnered with U.S. blockchain company Factom to build a national land registry. A 2015 audit of Honduras's existing land registry uncovered more than 700 corruption-related irregularities. The project stalled for "political reasons" — the officials responsible for those irregularities were the same officials who had to approve the new system [3]. **Lesson: a system that requires government permission inherits government corruption.**

**Republic of Georgia / Bitfury:** Georgia hashed existing land records to a blockchain. The system ran but had minimal impact — because it digitized records that had been created under a corrupted system. Making bad records immutable preserved the injustice. **Lesson: digitizing corrupt records does not make them trustworthy.**

**Sweden / ChromaWay (2016):** Sweden built a technically functional blockchain land registry. It stalled because Swedish law requires physical pen-and-paper signatures on property contracts — one legal technicality blocked a working system [4]. **Lesson: systems that operate within existing legal frameworks inherit existing constraints.**

**Bitland / Ghana (2014–present):** Launched with genuine ambition to address Ghana's severe land registration deficit (approximately 78% of land unregistered). After more than ten years, it has not delivered meaningful scale — undermined by infrastructure challenges, the complexity of reconciling new registrations against conflicting old records, and no path from community documentation to economic recognition [5]. **Lesson: technology alone does not solve adoption, and documentation without permanence or economic activation is insufficient.**

### 2.2 NGO and Institutional Programs

**Cadasta Foundation (2015–present):** Has documented land rights for over one million people across seventeen countries. High user satisfaction but documentation without permanence — records exist only as long as the organization maintains them, with no economic activation pathway [6].

**World Bank Land Titling Programs:** Decades of programs across Africa, Asia, and Latin America have consistently underdelivered. In Tanzania, fewer than one-third of promised land certificates were delivered five years into a program. Even when delivered, promised benefits — credit access, improved women's rights, reduced conflict — frequently failed to materialize [7]. Programs designed top-down by outsiders often destroyed existing communal and customary rights while creating new individual titles that did not fit local social reality.

### 2.3 The Pattern

Across all failures, the same themes recur: dependence on institutional permission; corruption of source data; legal framework constraints; organizational fragility; documentation without permanence or economic activation; and top-down design that ignores local tenure systems.

Landos is designed specifically to avoid each of these failure modes.

---

## 3. The Landos Protocol

### 3.1 Overview

Landos is an application-specific blockchain built on the Cosmos SDK with Tendermint BFT as its consensus base layer. On top of this foundation, Landos runs Proof of Land — a novel consensus model where validator weight is determined not by liquid token stake alone, but by demonstrated real-world land ownership and community standing.

The protocol maintains a global registry of land Parcel Records, each identified by a canonical Coords URI. Ownership of each parcel is represented by a Land Record NFT (Deed). The Landos Equity Token (LOS) provides fungible economic exposure to the aggregate value of the network.

Records are periodically anchored to the Bitcoin blockchain via OpenTimestamps, ensuring permanent proof of existence independent of the Landos network itself.

### 3.2 Three-Layer Asset Model

Landos is built on three layers:

**Layer 1 — The Parcel Record**

The Parcel Record is the foundational protocol primitive. It represents the on-chain existence of a specific piece of geography — a registered fact about a location on Earth. The Parcel Record is not a tradeable asset; it is a protocol-level record that everything else is built on top of.

Each Parcel Record contains:
- A canonical Coords URI identifying the geographic location
- The parcel's current ownership status
- A complete, immutable history of every status transition
- Optional Z-range fields supporting three-dimensional ownership (surface default for most parcels; vertical extent for underground resources, air rights, and multi-story structures)

Parcel Records support a full lifecycle: creation, boundary adjustment (requiring neighbor quorum from both sides), subdivision (retiring the original and creating new records with preserved lineage), consolidation (merging adjacent parcels), and retirement. Every modification preserves full on-chain lineage — a record created today should be fully traceable fifty years from now.

**Layer 2 — The Land Record NFT (Deed)**

The Land Record NFT is the on-chain deed — a CW721 non-fungible token uniquely tied to a specific Parcel Record. Ownership of the NFT constitutes ownership of the land on the Landos chain.

Key properties: one NFT per parcel; keyed to the Coords URI; ownership transfer requires the current owner's private key signature; the NFT carries the parcel's current ownership status; metadata is stored permanently on-chain.

To a non-technical user, the Land Record NFT is simply "the deed." They do not need to understand NFT mechanics to understand what it means.

**Layer 3 — The Landos Equity Token (LOS)**

LOS is a fungible token representing economic exposure to the aggregate value unlocked by Landos — analogous to a global land REIT. Holding LOS does not confer ownership of any specific parcel.

LOS captures the economic value of Landos's core function: converting dead capital into live capital. Every parcel registered on Landos moves from economically inert to economically active. That transformation has real aggregate value. LOS is the instrument through which that value is accessible to anyone in the world.

Additional instruments — leases, liens, easements, resource rights — can be built on top of these three layers as the network matures, each mapping to a real-world financial instrument.

### 3.3 Land Identification

Every piece of land on Landos is identified by a **Coords URI** — an open, CC0, tamper-evident coordinate identifier defined by the Coords protocol (github.com/coordsapp). Coords URIs are derived purely from WGS84 geography, belong to no government or institution, and are universally unique.

The **Coords XREF System** maps every major spatial identification system — H3, What3Words, WGS84, GeoJSON, Plus Codes, MGRS, postal addresses, and national cadastral registries — to a canonical Coords URI. Any ID from any system resolves to one Landos location. This means a farmer who arrives with a government parcel number, a GPS coordinate, or an Open Tenure record can all register the same parcel through the same system.

---

## 4. Ownership Validation

### 4.1 Philosophy

Establishing that a person owns a piece of land is a human and social problem, not just a technical one. People know who lives where. Communities know their own members. Landos encodes that social knowledge into the protocol cryptographically.

No single mechanism is sufficient. Together, five interlocking mechanisms make false claims very hard to establish and very hard to maintain.

### 4.2 Five Validation Mechanisms

**Proof of Habitation**

A landowner proves physical presence at their registered land over time using a mobile app. Every verified period of presence — confirmed via GPS, device accelerometer (proving natural movement), and randomized check-ins — accumulates into a habitation score. Time is the proof. A real owner who has lived on their land for years accumulates evidence that cannot be faked at scale or purchased with money. Habitation score contributes 60% of validator weight in Proof of Land consensus.

**Neighbor Quorum**

Inspired by Bitcoin's multisig wallet design. The Neighbor Quorum requires M-of-N neighbors to cryptographically sign a land claim with their own private keys — a cryptographic act that puts their own standing behind the claim. Default parameters: 3-of-5. A false claim requires corrupting multiple independent neighbors simultaneously, which is far harder than forging a single document.

**AR Boundary Walking**

A neighbor or validator physically walks the boundary of a parcel with a phone running the Landos app. The app overlays the registered boundary on the real world through the camera. GPS logs the validator's position. A liveness challenge proves physical presence. At least two independent validators must walk the same boundary before a boundary confirmation is recorded.

**Delegated Vouching**

A landowner assigns trusted parties — community leaders, local organizations, Open Tenure workers — who can sign attestations on their behalf. The delegation is on-chain, revocable, and does not transfer ownership.

**Community Memory**

Attestation statements from neighbors and community members accumulate over time into a permanent, cryptographically signed, Bitcoin-anchored record of community knowledge about each parcel. A parcel with years of community memory is extremely difficult to fraudulently contest.

### 4.3 The Staged Entry Model

Bad data entering the chain is a greater risk than slow entry. Landos treats friction at the entry point as a security feature — modeled on Bitcoin's deliberate ten-minute block time.

A claim must pass through four sequential stages before reaching Confirmed status. Each stage has a minimum duration of seven days. Minimum time to Confirmed: **28 days**. Stages may run partially in parallel but cannot be skipped.

| Stage | Duration | Gate |
|---|---|---|
| 1. Notice Period | 7 days | Claim visible to Community Hub; objections surface |
| 2. Neighbor Quorum | 7 days | Required independent attestations completed |
| 3. Habitation | 7 days minimum | Physical presence demonstrated; accumulates indefinitely |
| 4. Land Witness Review | 7 days | Neutral third party certifies process was followed correctly |

**Confirmation Depth:** Confirmed is not binary. A claim confirmed last month is easier to challenge than one confirmed five years ago with no disputes. Confirmation depth accumulates over time, mirroring how courts treat a century of clean title history differently from a one-year-old deed.

Stage durations are initial parameters, adjustable through governance based on observed network behavior.

---

## 5. Griefing Defense

Griefing — filing bad-faith claims against real landowners not to succeed but to cause harm — is a distinct attack vector that purely economic barriers cannot address. Landos defends against griefing through five interlocking mechanisms.

**Land Witness:** A neutral third party with no relationship to either party and no stake in the outcome certifies transactions and attestations. Structurally excluded from being a beneficiary of any claim they certify.

**Interested Party Exclusion:** Protocol-enforced conflict of interest blocking. A neighbor with an adjacent active claim cannot participate in a quorum for the parcel they border. A family member named in a succession record cannot serve as a recovery contact for that account.

**Personal Validation Score (PVS):** Every account accumulates a cumulative on-chain record of honest participation. PVS grows slowly through legitimate attestations and certifications. It is damaged by bad behavior and never resets. Low-PVS accounts attempting claims against confirmed parcels trigger additional scrutiny and higher bond requirements.

**Hold Period:** Any claim filed against a confirmed parcel triggers an automatic waiting period before any action can be taken. The existing owner is notified immediately. No transfer, recovery, or status change can occur until the Hold Period expires. Initial parameter: 7 days, calibrated to parcel confirmation history.

**Dispute Bond:** Filing a claim against a confirmed parcel requires staking LOS. The bond is forfeited in full if the claim is found to be bad faith — a portion awarded to the existing owner, the remainder burned or returned to the network treasury. Bond amount calibrated to be a meaningful deterrent without blocking legitimate disputes.

Together: a serial griefer loses PVS on every failed attempt, raising their bond requirement on subsequent attacks. The system gets progressively more expensive to abuse.

Dispute resolution is local and human — Land Witness plus Community Hub plus PVS-weighted arbitration. Token holder votes play no role in individual disputes. The woman defending her parcel should not have her case decided by a token whale with no relationship to her land.

---

## 6. Privacy Architecture

### 6.1 The Privacy Problem

A fully public land registry creates risk for landowners in certain contexts. A woman whose ownership is publicly visible in a conflict zone may be endangered. An indigenous community whose territorial boundaries are on-chain may be providing a map to people who want to take that land.

This tension — between the transparency that makes a blockchain trustworthy and the privacy that keeps its users safe — has stalled every previous blockchain land project that attempted to address it.

### 6.2 Two-Layer Architecture

Landos resolves this tension through a two-layer architecture:

**Public Layer:** The Landos blockchain stores only W3C Decentralized Identifiers (DIDs) and zero-knowledge proofs. A DID is a self-sovereign identity that no central authority controls. Zero-knowledge proofs allow the chain to verify that a claim is legitimate — that identity verification passed, that habitation was demonstrated, that a quorum was met — without revealing the underlying personal data. The public chain never sees a real name, a government ID, or a precise location beyond what the registered Parcel Record itself contains.

**Private Layer:** A separate, off-chain infrastructure maps real identities to DIDs. This layer is operated under strict access controls, maintained in a separate private repository, and governed by explicit data protection policies. Real identity data is never stored on the public chain.

### 6.3 Zero-Knowledge Technology

Landos uses **zkSNARKs** (Zero-Knowledge Succinct Non-Interactive Arguments of Knowledge) implemented via **gnark** — a Go-native ZK proof library that integrates directly with the Cosmos SDK.

zkSNARKs are production-ready as of 2026, widely deployed in financial privacy applications, and well-suited to the identity and location verification requirements of Landos. They allow the protocol to prove: "this person passed identity verification" and "this person was present at this location" — without revealing who the person is or their exact GPS history.

Identity verification is handled by Persona (initial partner) using W3C Verifiable Credentials. Landos stores only the signed credential — proof that verification passed — never the underlying biometric or identity data.

---

## 7. Node Architecture

### 7.1 Three Node Types

The strength of the Landos network depends on the distribution and independence of its nodes. Landos uses three node types:

**Full Nodes** store the complete Landos blockchain and independently validate every transaction and protocol rule. No node is trusted — every full node verifies everything itself. Full nodes earn the highest LOS rewards and form the security backbone of the network.

**Light Nodes (SPV)** store block headers only and verify specific transactions against Merkle proofs provided by full nodes. They trust the chain's proof-of-work, not any individual node — the same model as Bitcoin's SPV. Light nodes can run on consumer hardware (laptop, Raspberry Pi) and earn smaller LOS rewards, making network participation accessible to a wider range of operators globally.

**Relay Nodes** store some or all of the chain and serve data on request. They do not validate — they are data pipes. A full node or SPV node receiving data from a relay node verifies it independently; a relay node cannot lie in a way that survives verification. Relay nodes earn modest LOS rewards for bandwidth and data availability only.

There are no geographic or regional node types. A node that holds only a regional subset of the chain cannot independently verify the full record and must trust someone else's view of the data it doesn't have. That trust is an attack surface. In regions where corruption is most likely, local control of a regional node is exactly the threat Landos is designed to eliminate.

### 7.2 Offline Operation

Landos is designed for regions with unreliable connectivity. Every signed transaction carries a sync header: chain tip, chain ID, client version, and device timestamp. This enables deterministic ordering of offline claims and gives validators context on device state at time of signing.

Community Hubs relay transactions via Bluetooth and WiFi Direct for areas without internet access. Coverage gaps are addressed over time by satellite networks — not a blocker for deployment.

### 7.3 Making Nodes Easy to Run

The easier it is to run a node, the more nodes exist. The more nodes exist, the more secure and decentralized the network. Node operation must be accessible to technically curious people without deep engineering expertise. This means simple installation, clear documentation, and hardware requirements that match the light and relay node tiers. This is a UX priority, not just an engineering consideration.

---

## 8. Consensus: Proof of Land

### 8.1 Base Layer

Landos uses Tendermint BFT consensus as its base layer, implemented via the Cosmos SDK. Tendermint is proven, energy-efficient, and handles distributed systems problems — node agreement, fork resolution, network partitions — without proof of work.

### 8.2 Application Layer: Proof of Land

On top of Tendermint, Landos runs Proof of Land — a consensus model where validator weight is determined by:

- **Habitation score (60%)** — accumulated proof of physical presence on registered land
- **Hub standing (20%)** — participation and reputation within a Community Hub
- **Attestations (20%)** — accumulated valid attestations from other network participants

Land ownership is a validator **qualifier** — a validator must be a registered landowner — but not a weight multiplier. Owning more land does not confer more consensus power. This prevents the plutocratic capture that affects pure proof-of-stake systems. The people who secure the network are the people whose land lives on the network — they have the most to lose if it fails.

### 8.3 Community Hubs

Community Hubs are geographic groupings of parcels whose registered owners share proximity. They emerge organically from registration density, not from political boundaries. Hubs provide local validator pools, community memory at the local level, local dispute resolution context, and hub-level governance participation.

A hub activates automatically when M-of-N registered landowners within X kilometers trigger the threshold. Overlapping hubs are acceptable — providing redundancy. Hub parameters will be calibrated during testnet.

---

## 9. Economic Model

### 9.1 The Landos Equity Token (LOS)

**Full name:** Landos Equity Token  
**Ticker:** LOS  
**Total supply:** 1,489,000,000 (1.489 billion)  
**Decimal places:** 8  
**Total sub-units:** 148.9 quadrillion — equal to Earth's land area in million km²

The supply is not arbitrary. 1.489 billion LOS × 10⁸ sub-units = 148.9 quadrillion total units, where 148.9 is Earth's land surface area in million km². The smallest unit of LOS maps to the fundamental physical reality this protocol exists to serve.

### 9.2 Supply Model

The LOS supply model follows Bitcoin's principles as closely as possible:

- **No pre-mine** — zero LOS issued before block 1
- **No foundation allocation** — the Landos Foundation is funded through the creator's personally earned LOS and external grants in the early phase
- **All LOS earned through participation** — node operation, validation work, habitation check-ins, and community attestations. LOS is earned by doing real work on the network.
- **Programmatic halving** — block rewards halve at fixed block intervals, calibrated to Landos's block speed. Exact interval determined at testnet.
- **Non-human-controlled** — the issuance schedule is written into the protocol at genesis and cannot be changed without full bicameral governance

This means the Foundation operates on earned LOS and external support in the early days, before LOS has meaningful market value. This constraint is intentional — it is the same constraint Bitcoin's creator accepted, and it keeps the supply model pure.

### 9.3 Fee Model

Transaction fees are the base operational model for the network, floating with demand — the same mechanism as Bitcoin. Fee complexity scales with transaction type: a simple habitation check-in costs almost nothing; a full boundary walk with multiple attestors costs more.

**Accessibility guarantee:** Registering land on Landos must cost nothing for the people Landos exists to serve. Two mechanisms ensure this:

**Earn through participation:** Real landowners accumulate small LOS rewards through habitation check-ins, community attestations, and Community Hub participation — enough to cover their own transaction fees just by being present on their land. The act of being a genuine landowner generates the currency needed to be on the chain.

**Hub subsidy:** Community Hubs maintain a LOS pool funded by network rewards. Basic registrations for hub members who have not yet accumulated sufficient LOS are covered by the hub pool.

Validation is the spam defense — not fees. The five-stage validation model with its 28-day minimum timeline makes fraudulent registrations expensive in time and community capital, not just money.

### 9.4 Node Economics

Node operators earn LOS through two mechanisms: uptime and availability (proportional to time online serving the network) and validation work (completing land claim confirmations, processing registrations, executing validation tasks). Relay nodes earn for availability only.

The design principle: running a node should always be economically rational once LOS has meaningful value, creating a self-reinforcing network effect where network security grows with network value.

---

## 10. Governance

### 10.1 Bicameral Structure

Landos uses a bicameral governance model designed to resist both wealth concentration and geographic concentration:

**Token Holder Assembly** — votes weighted by LOS holdings using quadratic voting (voting power = square root of tokens held), which resists whale capture while preserving economic stakeholder participation.

**Community Hub Assembly** — one hub, one vote, regardless of hub size or token holdings. Resists geographic concentration by giving equal voice to every active community hub.

Both chambers must reach a **two-thirds supermajority** for any protocol change to pass. All approved changes are subject to a **90-day time lock** before taking effect, giving the community time to respond to changes they oppose.

### 10.2 Governance Activation

The genesis block encodes a governance activation block height, equivalent to approximately one year of block production. Before this height, the creator holds temporary admin keys enabling rapid iteration during the network's earliest phase. After this height, admin keys are permanently gone. There is no override. There is no recovery. All changes from that point require full bicameral governance.

Block height — not calendar time — governs this transition, so it adjusts naturally to the actual date of mainnet launch.

### 10.3 Creator Standing

The creator retains elevated governance weight during the period before the governance activation block. There is no hard-coded decay or forced exit timeline — the creator chooses when to step down from this elevated standing. This is transparent and declared at genesis.

---

## 11. The Landos Foundation

The Landos Foundation is a minimal operational entity that exists to do the human work the protocol cannot do in its earliest phase.

**What it does:** hiring and managing Community Ambassadors and support workers; compensating workers in LOS; coordinating early development and documentation; serving as a contact point for external parties during early adoption.

**What it does not do:** control the protocol; hold user funds, keys, or land records; alter or freeze land registrations; make governance decisions; veto node operators or validators.

**Accountability:** The Foundation's LOS holdings, expenditures, and decisions are publicly documented. Its mandate is defined and limited at the protocol level.

**Trajectory:** The Foundation is designed to wind down as the network matures — its functions progressively transferred to protocol automation, community governance, and the decentralized node network. Its goal is to make itself unnecessary.

Community Ambassadors are the human face of Landos in its early years — traveling to communities, building trust, answering the question "who is behind this?" with a real name and face. As Community Hubs mature, the Ambassador role phases down.

---

## 12. Security

### 12.1 No Off Switch

Landos is designed to have no off switch.

- No central server — nodes run across many jurisdictions globally
- No foundation that controls the protocol — the Foundation handles operations; it does not control the chain
- No CEO — no individual to arrest or coerce
- Open source — the code is publicly verifiable by anyone
- Bitcoin anchored — records survive even if Landos is attacked
- Geographic distribution — shutting Landos down would require simultaneous action across dozens of countries
- Community Hub structure — thousands of independent local hubs with no single point of failure

### 12.2 Bitcoin Anchoring

Landos records are periodically anchored into the Bitcoin blockchain using OpenTimestamps — an open protocol developed by Bitcoin developer Peter Todd. This means even if Landos itself were attacked or destroyed, proof that land records existed at specific moments in time lives permanently in Bitcoin. No one can erase it.

Bitcoin has operated continuously since 2009 without successful alteration. It is the most durable digital record system ever created. For records that families may rely on for generations, only the most durable anchor is good enough.

### 12.3 Key Recovery

Private key loss is a real threat to users. Landos handles this through a dedicated recovery portal — separate from the main interface — that facilitates key rotation (invalidating the old key and issuing a new one) without ever storing or seeing private keys.

At account creation, users register three recovery factors: a primary email, a PIN, and three recovery contacts (neighbors or trusted community members with active Landos accounts, re-confirmed annually). Recovery paths are tiered by which factors remain intact, with a 72-hour time-lock on all recovery attempts. AI-assisted automation handles most cases; human support workers handle edge cases and are compensated in LOS.

---

## 13. Roadmap

Landos is in active design phase. No network exists yet.

**Phase 1 — Design Stabilization**
Resolve remaining protocol parameters through continued design work and legal consultation. Complete privacy layer design. Establish Foundation legal jurisdiction. Finalize node reward economics.

**Phase 2 — Testnet**
Launch testnet with a small number of full nodes. Calibrate halving interval, hub activation parameters, fee economics, and stage timing. Real-world registration testing with Community Ambassadors in initial deployment regions.

**Phase 3 — Mainnet**
Genesis block production. LOS issuance begins. First community registrations. Foundation operational — Community Ambassadors active. Governance activation block programmed.

**Phase 4 — Governance Activation**
Governance activation block reached. Admin keys permanently removed. Bicameral governance fully operational. Foundation begins phased wind-down.

**Initial Deployment Regions**
Ghana is the first priority region for Community Ambassador activity and early registration, given the severity of the land registration deficit and the presence of an established community network.

---

## 14. Conclusion

Land ownership has been insecure and economically dead for hundreds of millions of people for as long as formal records have existed. Every attempt to fix this through institutional channels has failed — captured by the same corruption it was designed to address, blocked by the same legal frameworks it needed to circumvent, or abandoned when the organizations behind it lost funding or will.

Landos takes a different approach. It does not ask permission. It does not require institutional cooperation. It does not depend on any single organization to persist.

It simply exists — the same way Bitcoin simply exists — and it invites the people who need it most to use it.

The technology is ready. The framework is proven. The people who need it have been waiting long enough.

> *"Land locked from its rightful owners is poverty by design. This chain breaks that lock — for everyone, forever, without permission."*

---

## References

[1] de Soto, H. (2000). *The Mystery of Capital: Why Capitalism Triumphs in the West and Fails Everywhere Else.* Basic Books.

[2] Nakamoto, S. (2008). *Bitcoin: A Peer-to-Peer Electronic Cash System.* bitcoin.org/bitcoin.pdf

[3] SiliconANGLE (2015). *Factom's Blockchain Land Registry Tool trial stalls due to the politics of Honduras.* siliconangle.com

[4] CoinDesk (2017). *Why Sweden is Taking a Chance on Blockchain Land Registry.* coindesk.com

[5] Borgen Project (2016). *Property Rights for The World's Poor — Bitland.* borgenproject.org

[6] Cadasta Foundation (2021). *Annual Report 2020.* cadasta.org

[7] Stein, H. (2024). *The World Bank and Rural Land Titling in Africa: The Case of Tanzania.* Development and Change. Wiley Online Library.

---

## Appendix A: Glossary

**Confirmation Depth** — the accumulated time and absence of challenges on a Confirmed parcel; determines how difficult the parcel is to contest.

**Community Hub** — a geographic grouping of registered landowners that emerges organically from registration density; provides local validation, dispute resolution, and governance participation.

**Coords URI** — a canonical, open, CC0 geographic identifier derived from WGS84 coordinates; the universal land identifier on Landos.

**Coords XREF System** — a cross-reference system mapping all major spatial identification systems to a canonical Coords URI.

**Deed** — see Land Record NFT.

**Dispute Bond** — LOS staked to file a claim against a confirmed parcel; forfeited if the claim is found to be bad faith.

**Hold Period** — mandatory waiting period before any action on a claim against a confirmed parcel; existing owner notified immediately.

**Interested Party Exclusion** — protocol-enforced rule preventing conflicted parties from attesting in situations where they have a stake in the outcome.

**Land Record NFT (Deed)** — a CW721 non-fungible token representing ownership of a specific Parcel Record; the on-chain deed.

**Land Witness** — a neutral third party with no stake in a claim who certifies that a transaction or attestation process was followed correctly.

**Landos Equity Token (LOS)** — the fungible economic token of the Landos network; represents aggregate economic exposure to land value unlocked by the protocol.

**Parcel Record** — the foundational protocol primitive; the on-chain fact that a specific piece of geography has been registered and validated.

**Personal Validation Score (PVS)** — a cumulative on-chain record of honest participation; grows slowly, damaged by bad behavior, never resets.

**Proof of Habitation** — accumulated cryptographic evidence of physical presence at a registered land location over time.

**Proof of Land** — Landos's application-layer consensus model; validator weight determined by habitation score, hub standing, and attestations.

**zkSNARK** — Zero-Knowledge Succinct Non-Interactive Argument of Knowledge; cryptographic proof that allows verification of a claim without revealing the underlying data.

---

*Landos Whitepaper v0.1.0 — Draft. All sections subject to revision as design matures.*
