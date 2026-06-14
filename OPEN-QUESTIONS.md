# Landos — Open Questions Log

This log tracks resolved design decisions and remaining open questions for the Landos design document. It is maintained separately from the main design doc (`spec/design/landos-design-vX.X.X.md`) to keep that document focused on the current design rather than its history.

Each resolved item references the design doc section where the decision is reflected. Each open item is a known gap or area needing further work, sized for community discussion.

---

## Resolved

- Token model: three layers (Parcel Record → Land Record NFT → LOS) ✓
- Full token name: Landos Equity Token (LOS) ✓
- LOS supply: 1,489,000,000 — no pre-mine, no foundation allocation, all earned through participation, programmatic halving ✓
- NFT standard: CW721 via CosmWasm ✓
- Fractional ownership: NFT stays whole, co-owners in metadata, M-of-N signatures required ✓
- Philosophical foundation: Bitcoin + de Soto as the two pillars ✓
- Node model: three types — full, light/SPV, relay; no geographic nodes ✓
- Node reward principles: fixed hierarchy, validation > uptime, Bitcoin halving curve, written into genesis; exact amounts TBD at testnet ✓
- Government relationship: legitimacy earned through adoption, not permission ✓
- Registration fee model: earn through participation + Hub subsidy pool; validation is spam defense, not fees ✓
- Key recovery: tiered paths via dedicated portal; email + PIN + 3 recovery contacts; 72-hour time-lock; AI automation + human escalation ✓
- Key recovery penalties: scales with information advantage; support workers held to higher standard ✓
- Key recovery worst-case: no last-resort path in v1; deferred to v2 ✓
- Landos Foundation: minimal operational entity, no protocol control, no incorporation before genesis ✓
- Griefing defense: five mechanisms — Land Witness, Interested Party Exclusion, PVS, Hold Period, Dispute Bond ✓
- Dispute Bond: held in escrow, scales with PVS + confirmation depth, Hub subsidy for legitimate claimants, Community Hub hears, Land Witness certifies ✓
- Staged entry model: four stages × 7 days = 28 days minimum to Confirmed ✓
- Confirmation depth: longer confirmed = harder to overturn ✓
- Proof of Habitation anti-gaming: liveness challenges, cross-signal anomaly detection, community corroboration ✓
- AR Boundary Walking anti-gaming: sensor fusion, video liveness, temporal cross-check, community spot-check ✓
- Hub activation threshold: adaptive by density; exact values TBD at testnet ✓
- Disputed territories: conflict zone overlay, staged cooldown, governance-controlled ✓
- Collective/community ownership: community wallets (M-of-N multisig) ✓
- Genesis block: contents locked — founding statement, LOS supply, governance rules, activation block ✓
- Z-axis: in architecture from genesis; hectare-meter unit deferred ✓
- Governance: bicameral (Token Holder Assembly + Community Hub Assembly), 2/3 supermajority, 90-day time lock ✓
- Whitepaper: v0.1.0 complete ✓
- LADM alignment: core classes mapped (Section 21) — Parcel Record ↔ LA_SpatialUnit, Land Record NFT ↔ LA_BAUnit + LA_Right, DIDs ↔ LA_Party/LA_GroupParty; conceptual/translational only ✓
- Individual-human identity principle: Landos is built around the individual person, not household/family/role/gender (Section 2, Pillar 1) — every person gets their own DID, co-ownership is a list of named individuals, no protocol concept of "head of household" ✓
- STDM alignment: Social Tenure Relationship (STR) maps to Section 13's status spectrum; overlapping/contested claims and evidence-based STRs validated against Land Witness, Dispute Bond, Proof of Habitation, AR Boundary Walking, Neighbor Quorum (Section 21.7) ✓
- Fit-For-Purpose cross-check: all five FFP principles (Flexible, Inclusive, Participatory, Affordable/attainable, Upgradeable) checked against existing Landos design decisions — no gaps found (Section 21.8) ✓
- VGGT framing: legitimate tenure independent of registration, protection against forced eviction, and access to justice mapped to existing sections; gender-sensitive tenure governance addressed structurally via the Pillar 1 individual-identity principle (Section 21.9) ✓
- Onboarding/social-graph review for gender-sensitivity in practice: resolved by the Independent Claimant Path below — registration no longer depends on the social graph at all, so "head of household" defaults can't enter through Stage 0 ✓
- Independent Claimant Path (v0.1.9): registration has no prerequisites — a claim can enter the status spectrum at Claimed with zero attestations (Section 13). Validation mechanisms (Section 11) are a menu, not a checklist: a claimant with no usable social graph leans on Habitation and AR Boundary Walking instead of Neighbor Quorum. When Neighbor Quorum can't be formed, two independent Land Witnesses substitute for it (Section 11.6, Section 13.1). The Notice Period remains hub-visible regardless of path, so a real neighbor can still raise a Contest even if never asked to attest. Section 20 onboarding now offers this as a first-class second entry point alongside "do you know your neighbor?" ✓

---

## Still Open

1. **Proof of Land scoring model** — model designed ✓ (Section 10.4); exact accumulation curve, decay rate, and confirmation threshold TBD at testnet
2. **Neighbor Quorum parameters** — 3-of-5 default; to be revisited as design matures
3. **Hub boundary definition** — how geographic hub boundaries are drawn without political boundaries TBD
4. **Succession and inheritance** — DEFERRED; likely its own app and repo; requires legal review
5. **Privacy / identity layer** — zkSNARKs via gnark decided; full design session needed
6. **Coerced registration defense** — NEEDS LEGAL CONSULTATION before further design
7. **Fractional ownership edge cases** — disputes between co-owners, forced sale, deceased co-owner TBD
8. **The mobile app** — validation layer depends on an app not yet designed; offline/low-connectivity required
9. **LA_Restriction / LA_Responsibility representation** — liens, easements, conservation restrictions, and tax obligations now have a named category (Section 21.4); on-chain representation (separate token types vs. NFT metadata fields vs. other) TBD
10. **3D spatial unit design** — LADM Edition II Part 5 confirms the need (Section 21.5); Landos's own hectare-meter unit design remains deferred
11. **Land Witness capacity for the Independent Claimant Path** — requiring two independent Land Witnesses (Section 11.6) assumes enough Land Witnesses exist per hub to cover claimants with no social graph; how Land Witnesses are recruited/trained at scale is still open. Working direction (not yet specced): assignment, not search — eligible pool = hub members above a standing threshold who opt into an on-call roster; random draw filtered by Interested Party Exclusion (applied pairwise for the two-witness case); non-response reassigns rather than penalizes; shortfalls escalate to overlapping/adjacent hubs; pool eligibility bar starts low and rises with hub maturity, same soft-threshold pattern as validator bootstrapping. To be revisited during testing.

---

*This log is updated alongside each design doc revision. See `community/CHANGELOG.md` for the version history of the design doc itself.*
