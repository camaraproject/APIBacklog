# New API Family Proposal: CarrierAttestation

> This is the filled API-proposal template for the CarrierAttestation API
> family proposal. It accompanies issue
> https://github.com/camaraproject/APIBacklog/issues/330. Source document
> (with the full normative profile):
> https://github.com/hamr0/justabit/blob/main/docs/product/camara-attested-windowed-disclosure.md
> §10, re-verified 2026-08-25.
>
> The proposal, PoC, and OpenAPI sketch referenced throughout this proposal
> live at https://github.com/hamr0/justabit (Apache 2.0, public, not itself
> a CAMARA deliverable — the author's own staging ground for this
> submission). See "Reference material" at the end of the References
> section for the direct links.
>
> **Framing, stated up front so the Working Group reads this proposal
> correctly:** this is not a request to approve a new, free-standing API.
> CAMARA already ships two structural precedents for exactly this shape of
> answer — `POST /retrieve-age-band` (SimSwap v2.1.0), which coarsens a raw
> timestamp into a band because the raw value over-discloses, and
> `GET /device-phone-number` (NumberVerification v2.1.0), which takes no
> request body at all and derives the line from the 3-legged access token
> instead of a supplied identifier. `kyc-age-verification` already ships a
> boolean age-threshold predicate in the catalog. The ask is to **finish
> what those three started, catalog-wide** — a horizontal profile
> ("attested windowed disclosure") that any existing API answering a
> question about a subscriber or device can adopt, so that a predicate
> answer is a signed, nonce-bound, expiring boolean and never the underlying
> raw value. `CarrierAttestation` is filed here, as a new API family, only
> for the residual that no existing catalog API can be adopted into: agent-
> grade floor bundles and holder-presentment (Mode B). The profile itself is
> proposed separately to Commonalities/ICM and to per-API adoption PRs (see
> the proposal doc §6) — this filing is the "new case" half only.

---

## Contact

- **Contact email:** avoidaccess@msn.com
- **Submitter:** Amr Hassan, Cairenes Solutions — independent telecom
  consultant (10 yrs wholesale roaming / signaling / SoR).

## API family name

CarrierAttestation

## API family owner

Cairenes Solutions

## API summary

Identity data should not become a tradeable asset. This family lets the
operator answer a boolean and keep custody of the underlying fact, and lets
an aggregator carrying the query meter and bill without ever reading
identifiers, predicates, or answers: signed, nonce-bound, expiring predicate
attestations over network facts operators already compute (SIM-swap age,
tenure, subscription class), under monotone floors — for the cases no
existing API covers: agent-grade floor bundles (proposal doc §3.4) and
holder presentment (proposal doc §5).

Business cases:
1. A bank authorizes a transfer on "unswapped ≥ 90d" without receiving a
   timestamp.
2. An AI agent presents a floor-gated carrier credential ("voice+data ∧
   tenure ≥ 2y ∧ swapAge ≥ 90d") to a service that never learns the MSISDN.
3. A content service verifies "device in licensed region" without location
   custody.

## Northbound API type

Service API.

## Scope fit with CAMARA

Customer-facing northbound exposure of telco network capabilities
(subscription facts, SIM lifecycle, network authentication); no
east-west/federation surface. The consumption modes this filing adds are
additive to existing catalog APIs, per Project Charter scope. The design
keeps any aggregator in the path a blind hub — metering and billing, never
reading identifiers, predicates, or answers — so the capability to
accumulate and monetize subscriber data against the ecosystem is removed by
construction rather than left to a middle layer's restraint.

## Proposal owner declaration

The proposal owner confirms this proposal has been reviewed against the
current CAMARA Project Charter scope (see References below) and fits
within it as described above.

## Telco capability exposed

Operator-held subscription and SIM-lifecycle facts (swap recency, tenure,
SIM type/class) plus network-session authentication (silent auth), exposed
as signed predicates rather than raw values.

## Overlap with existing CAMARA APIs

Reviewed 2026-08-14, re-verified 2026-08-24. No overlap. Existing APIs
(sim-swap, number-verification, kyc-age-verification) are the *adoption
targets* of the horizontal profile (proposed separately via Commonalities);
CarrierAttestation covers only what none of them expose: floor-bundle
attestations and holder presentment.

## Explicit out-of-scope items

- Raw-value retrieval of any kind.
- Identity assertion (no name/document facts).
- Consent framework changes (rides on ICM).
- The aggregator's commercial model (unchanged by design — per-query
  billing and revenue share continue as today).

## Technical viability

Every attested fact is already computed for existing catalog APIs; issuance
authentication is the same network-auth mechanism `number-verification`
uses today; signing/verification is SD-JWT VC + JWKS per PLMN (standard
tooling operators need for eIDAS 2.0 regardless).

## Commercial viability

Open-source reference PoC at
https://github.com/hamr0/justabit/tree/main/poc (Node.js, zero
dependencies); SD-JWT VC / OpenID4VCI/VP open-source stacks are available;
per-query billing is preserved in Mode A by construction — the aggregator
meters and bills but is structurally unable to read identifiers,
predicates, or answers.

## YAML code available

YES — illustrative sketch at
https://github.com/hamr0/justabit/blob/main/spec/carrier-attestation.yaml
(non-normative draft; predicate ids in it are illustrative spellings, not a
normative enumeration).

## Validated in lab/productive environments

YES, sandbox tier only. The Mode A PoC was run live against the Orange
Network APIs Playground, an operator public sandbox environment (not a
production network), exercising Orange's test tier with scripted test
numbers. User-run, by exit code, all green: `m5-check-live.mjs` 20/20 and
`demo.mjs --backend orange` 35/35 (CHANGELOG 0.5.0, 2026-08-18), with an
injected clock and quota accounted 1-of-10 custom slots at both start and
end. No production environment has been exercised, and no operator
endorsement is implied by this validation.

## Validated with real customers

NO.

## Validated with operators

NO — no operator has reviewed or validated this proposal. Naming
supporters is Working Group business that happens during evaluation,
downstream of filing (see the Supporters field below); no recruitment is
currently underway.

## Supporters in API Backlog Working Group

*Left blank per the template's own instruction: "List of supporters. NOTE:
That shall be added by the Working Group." Our own targeting note, not a
claim of existing support: ICM's privacy-forward operator pool — DT,
Orange, Telefónica — looks like the likely fit to approach once this
proposal is filed.*

---

## Known limits and open questions

The following residuals are stated
plainly rather than smoothed over, because a Working Group reviewer will
ask about them and a proposal that omits them reads as unaware, not clean:

- **Mode A retains the operator-side query log.** The operator always knows
  it attested fact T about subscriber S at time t. Acceptable where the
  requester already holds its customer's number (KYC, fraud); only holder
  presentment (Mode B, roadmap) removes it.
- **Economic scarcity is not uniqueness.** The agent-grade floor (§3.4 of
  the proposal doc) raises the cost of an agent identity; it does not
  create uniqueness. One subscription can back many agents. "One
  accountable human" requires a document-rooted principal layer above this
  profile, which this filing does not provide and does not claim to.
- **The trust directory is a centralization point.** Verifiers need
  operator public keys per PLMN; governance of that directory belongs with
  existing GSMA key-distribution rails (RAEX/IR.21-shaped) and is the one
  unavoidable centralization point in this design.
- **MNP breaks naive tenure.** Porting resets the operator relationship, so
  a naive `tenure ≥ 2y` floor punishes honest porters, not farms. This is
  an open design question (proposal doc §9.8), not resolved by this
  filing.

## Terminology

Mode A — the mode this filing's business cases and validation evidence
describe — is **attested windowed disclosure**. It is not zero-knowledge, and
the author does not claim it as such anywhere in this proposal or any
follow-up. Zero-knowledge terminology applies only to Mode B (holder
presentment), which is roadmap, not what is being filed for evaluation
here.

## References

- CAMARA API Backlog process & template:
  https://github.com/camaraproject/APIBacklog
  (`documentation/APIbacklog.md`; `documentation/API-proposal-template.md`,
  re-verified 2026-08-14, re-verified again 2026-08-24 and 2026-08-25;
  filled examples under `documentation/SupportingDocuments/API proposals/`)
- CAMARA governance/structure: https://camaraproject.org/structure/ ·
  https://github.com/camaraproject/Governance/blob/main/ProjectStructureAndRoles.md
  · Project Charter:
  https://github.com/camaraproject/Governance/blob/main/ProjectCharter.md
- Verified spec baseline (2026-08-14, re-verified 2026-08-24): SimSwap
  v2.1.0 (`/check`, `/retrieve-date`, `/retrieve-age-band`):
  https://github.com/camaraproject/SimSwap · NumberVerification v2.1.0
  (`/verify`, `/device-phone-number`; TS.43 or OIDC `prompt=none`,
  3-legged, AMR-validated):
  https://github.com/camaraproject/NumberVerification · KnowYourCustomer
  split into three repos post-Spring25: kyc-match (r1.2, v0.4.0)
  https://github.com/camaraproject/KnowYourCustomerMatch · kyc-fill-in
  (r1.3, v0.4.1)
  https://github.com/camaraproject/KnowYourCustomerFill-in ·
  kyc-age-verification (r1.3, v0.2.1, Sandbox per its lifecycle badge,
  though its own README body text still says "Incubating stage since
  February 2025" — a contradiction, not resolved here)
  https://github.com/camaraproject/KnowYourCustomerAgeVerification
- One existing implementation of the document-rooted principal layer
  referenced in the "agent-grade floor" business case above exists in the
  authors' prior work (8een/zkagent). This proposal is standards-neutral
  and does not depend on it — it is cited as one implementation, not a
  dependency.

### Reference material

The following is the author's own staging ground for this submission —
Apache 2.0, public, and not itself a CAMARA deliverable:

- Repo root: https://github.com/hamr0/justabit
- CAMARA proposal document (full normative "attested windowed disclosure"
  profile): https://github.com/hamr0/justabit/blob/main/docs/product/camara-attested-windowed-disclosure.md
- Reference PoC (Mode A, Node.js, zero dependencies): https://github.com/hamr0/justabit/tree/main/poc
- OpenAPI sketch (illustrative, non-normative): https://github.com/hamr0/justabit/blob/main/spec/carrier-attestation.yaml
