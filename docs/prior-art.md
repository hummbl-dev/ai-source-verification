# Prior Art and Adjacent Ecosystem

This document surveys public prior art and adjacent ecosystem references
relevant to AI source verification. It closes issue #2 ("Collect prior art
and adjacent ecosystem references").

## Non-canon note

This is a **reference survey**, not a normative bibliography. Listing an
effort here does not imply endorsement, adoption, or canonization. Vocabulary
terms are attributed to their origin efforts and are not redefined as
proprietary here. Where this repo reuses a term, it does so descriptively,
not as a claim of ownership.

## Public prior art

### C2PA (Coalition for Content Provenance and Authenticity)

- **What it does:** Defines a standard for attaching cryptographically
  signed provenance and editing history to media (images, video, audio,
  documents) via a signed manifest embedded in or alongside the asset.
- **Relevance:** The closest public analog to a "verification packet" for
  media. C2PA manifests, claims, and assertions directly inform the
  `verificationManifest` and `verificationContract` shape in this repo's
  v0.1 schema.
- **Docs:** https://c2pa.org/specifications/

### Content Authenticity Initiative (CAI)

- **What it does:** An Adobe-led initiative implementing C2PA as
  "Content Credentials" — a user-facing label and a technical manifest
  describing asset origin and edits.
- **Relevance:** Provides the deployment surface and UX pattern for
  presenting provenance to end users. Relevant to how a v0.1 packet might
  be surfaced for human review.
- **Docs:** https://contentauthenticity.org/

### Sigstore

- **What it does:** Provides keyless code signing using ephemeral keys
  backed by OpenID Connect identities, with a transparency log of signed
  artifacts.
- **Relevance:** A model for how a verification packet's `authority` and
  receipt could be signed without long-lived keys. Relevant to
  `receiptRequirements` in v0.1.
- **Docs:** https://docs.sigstore.dev/

### Rekor

- **What it does:** Sigstore's append-only transparency log that records
  signed artifacts and their metadata for later audit.
- **Relevance:** A model for an auditable receipt store. v0.1 does not
  embed a transparency log, but `receiptRequirements` is designed to be
  compatible with a Rekor-style log in later versions.
- **Docs:** https://github.com/sigstore/rekor

### Witness (in-toto-based build attestation)

- **What it does:** A tool by TestifySec that records attestations about
  how artifacts were built, using in-toto layouts and a transparency log.
- **Relevance:** A concrete example of binding "how this was produced"
  evidence to an artifact. Relevant to `provenanceChain` and
  `attestationSpec` in v0.1.
- **Docs:** https://github.com/testifysec/witness

### in-toto

- **What it does:** A framework defining attestations about the steps of
  a software supply chain, signed by authorized actors at each step.
- **Relevance:** The structural model for a step-wise provenance chain.
  v0.1's `provenanceChain` is a simplified, single-packet analog.
- **Docs:** https://in-toto.io/

### SLSA (Supply-chain Levels for Software Artifacts)

- **What it does:** A security framework with graduated levels describing
  how much trust to place in a software artifact's provenance.
- **Relevance:** A model for graduated trust levels. v0.1 deliberately
  does not define levels, but `trustPolicy` is shaped to allow a
  SLSA-style level field in later versions.
- **Docs:** https://slsa.dev/

### Truepic

- **What it does:** Provides cryptographically authenticated capture for
  images and video, embedding provenance and integrity signals at capture
  time.
- **Relevance:** A deployment example of capture-bound provenance, useful
  for the `sourceType` vocabulary in v0.1.
- **Docs:** https://truepic.com/

## Adjacent ecosystem

### Project Origin

- **What it does:** A coalition (BBC, Microsoft, CBC/Radio-Canada, NYT)
  exploring content credentials and provenance for news and media.
- **Relevance:** Adjacent deployment context for media provenance at
  publisher scale.
- **Docs:** https://www.originproject.info/

### BBC Content Credentials

- **What it does:** BBC's exploration of C2PA-based content credentials
  for news images and video.
- **Relevance:** A real-world newsroom deployment pattern relevant to
  review expectations in v0.1.
- **Docs:** https://www.bbc.co.uk/rd/blog/2023-11-content-credentials

### ProofMode

- **What it does:** An open-source mobile library by Guardian Project that
  captures signed metadata (location, time, device) alongside photos and
  video.
- **Relevance:** A lightweight, capture-side provenance model relevant to
  `sourceType` and `provenanceChain` for non-studio capture.
- **Docs:** https://proofmode.org/

### OpenTimestamps

- **What it does:** Anchors hashes of documents into the Bitcoin blockchain
  to prove a document existed at a given time, without revealing content.
- **Relevance:** A minimal timestamping receipt model. Relevant to
  `receiptRequirements` for low-cost, externally-verifiable receipts.
- **Docs:** https://opentimestamps.org/

### OriginStamp

- **What it does:** A service that anchors file hashes to multiple
  blockchains to create tamper-evident timestamps.
- **Relevance:** A commercial analog to OpenTimestamps; same relevance to
  receipt anchoring.
- **Docs:** https://originstamp.com/

### ContentTrace

- **What it does:** Emerging work on tracing content origin and edits
  across AI-mediated pipelines.
- **Relevance:** Directly adjacent to this repo's domain; tracked but not
  adopted.
- **Docs:** (public references tracked; no canonical URL asserted here)

### Deepfake detection tools

- **What it does:** Classify media as synthetic or manipulated, typically
  via ML models.
- **Relevance:** Adjacent but distinct: detection infers manipulation
  after the fact, while source verification records provenance at
  production time. v0.1 does not include detection signals, but a later
  `attestationSpec` could reference them.
- **Docs:** Varied; no single canonical reference.

## Vocabulary

Terms used descriptively in this repo, attributed to their origin contexts.
None are redefined as proprietary here.

- **Provenance** — the recorded origin and history of an artifact. (C2PA,
  in-toto, SLSA)
- **Attestation** — a signed statement about an artifact or process.
  (in-toto, Sigstore, SLSA)
- **Content credentials** — a user-facing label and technical manifest for
  media provenance. (CAI/C2PA)
- **Source verification** — confirming the origin and integrity of a piece
  of work. (general)
- **Tamper detection** — detecting that an artifact has been altered.
  (C2PA, deepfake detection)
- **Watermarking** — embedding a persistent signal in media to identify
  origin or ownership. (C2PA, CAI)
- **Fingerprinting** — deriving a compact identifier from content to
  match or detect it. (general)

## Key concepts

- **Cryptographic provenance** — provenance backed by signatures or hashes
  rather than claims alone.
- **Content authenticity** — the property that an artifact's origin and
  edit history are credibly attested.
- **Manifest** — a structured record describing an artifact and its
  provenance. (C2PA, in-toto)
- **Claim** — a single asserted statement within a manifest. (C2PA)
- **Assertion** — a signed or declared statement about an artifact.
  (C2PA, in-toto)
- **Signature** — a cryptographic binding of an identity to a payload.
- **Verification** — the act of checking claims, signatures, and chains
  against a policy.
- **Trust chain** — an ordered set of attestations where each step is
  authorized by the prior. (in-toto, SLSA)

## Closing note

This survey is intentionally non-exhaustive. It exists to ground v0.1 in
existing public work and to prevent accidental re-invention or
over-claiming. Additions should be proposed via PR with a public doc link.
