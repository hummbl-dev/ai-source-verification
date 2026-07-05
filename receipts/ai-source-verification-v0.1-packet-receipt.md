# Verification Packet Receipt — v0.1

This is a candidate receipt template for a v0.1 AI Source Verification
packet. It is a review aid, not a legal instrument, and it is non-canon
until adopted through the governance path described in `CONTRIBUTING.md`.

## Packet reference

- **Schema version:** `ai-source-verification/v0.1`
- **Packet id:** _<fill in `verificationManifest.id`>_
- **Packet title:** _<fill in `verificationManifest.title`>_
- **Packet version:** _<fill in `verificationManifest.version`>_
- **Scope:** _<fill in `verificationManifest.scope`>_

## Producer authority

- **Producer:** _<fill in `authority.producer`>_
- **Basis:** _<fill in `authority.basis`>_

## Contract summary

- **Source type:** _<fill in `verificationContract.sourceType`>_
- **Provenance steps:** _<count of `verificationContract.provenanceChain`>_
- **Attestation format:** _<fill in `verificationContract.attestationSpec.format`>_
- **Trust level:** _<fill in `verificationContract.trustPolicy.level`>_
- **Verification status:** _<fill in `verificationContract.verificationStatus`>_

## Review checklist

A reviewer must confirm each of the following before signing this receipt:

- [ ] Packet validates against `schemas/ai-source-verification-v0.1.json`.
- [ ] `verificationManifest` correctly identifies the work, version, and scope.
- [ ] `authority.producer` and `authority.basis` are accurate.
- [ ] `verificationContract.provenanceChain` reflects the actual production
      history of the work.
- [ ] `verificationContract.attestationSpec.claims` are true to the best of
      the reviewer's knowledge.
- [ ] `verificationContract.trustPolicy` is appropriate for the work's use.
- [ ] `verificationContract.verificationStatus` is correctly set.
- [ ] `receiptRequirements` matches this receipt.

## Reviewer signoff

- **Reviewer:** _<fill in reviewer identity>_
- **Date (UTC):** _<YYYY-MM-DD>_
- **Decision:** _[ reviewed | rejected ]_
- **Notes:** _<optional>_

## Receipt anchoring (optional, later versions)

If this receipt is anchored to a transparency log or timestamping service,
record the reference here. v0.1 does not require anchoring.

- **Service:** _<e.g. Rekor, OpenTimestamps, OriginStamp>_
- **Reference:** _<log index / transaction id / hash>_

## Non-canon notice

This receipt, the packet it covers, and the schema it validates against are
all candidate artifacts. Signing this receipt marks the packet as reviewed
within this repo's process; it does not constitute a legal attestation, a
conformance claim, or an adoption of canon.
