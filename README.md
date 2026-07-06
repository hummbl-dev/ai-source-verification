# AI Source Verification

AI Source Verification is a public seed repository for source verification for AI-mediated work.

## Purpose

Source, citation, provenance, and claim-verification patterns for AI-mediated work.

## What Source Verification Means

Source verification is the practice of keeping claims connected to the materials that support them. In this repository, that means documenting how a statement, citation, artifact, or AI-mediated output can carry enough provenance for a reviewer to inspect where it came from and what evidence it depends on.

This repository focuses on reviewable packets and examples. It does not assert that a packet proves truth by itself; it helps readers separate cited evidence, declared claims, and verification status.

## Relationship to C2PA and Content Authenticity

C2PA and content authenticity systems help preserve provenance for media and signed assets. This repository is adjacent to that ecosystem: it explores lightweight schemas and examples for AI-mediated source, citation, and claim review.

The current v0.1 materials should be read as exploratory packet patterns, not as a replacement for C2PA manifests, cryptographic signing, or formal trust infrastructure.

## Status

Early public seed repository. Candidate namespace only.

## v0.1 Packet Map

- Schema: [schemas/ai-source-verification-v0.1.json](./schemas/ai-source-verification-v0.1.json)
- Example packet: [examples/verification-packet-v0.1.example.json](./examples/verification-packet-v0.1.example.json)
- Boundary notes: [docs/v0.1-boundary.md](./docs/v0.1-boundary.md)
- Contribution process: [CONTRIBUTING.md](./CONTRIBUTING.md)

## Goals

- Define the domain clearly.
- Collect prior art and adjacent ecosystem references.
- Provide reusable schemas, examples, and templates.
- Support human review and agent execution.
- Preserve provenance, auditability, and governance boundaries.

## Non-goals

- This repo is not a universal standard.
- This repo does not claim ownership of the broader field or terminology.
- This repo does not canonize HUMMBL/BaseN/Ownward concepts unless explicitly marked and audited.
- This repo must not include private, internal, or secret operational content.

## Boundary

All content is exploratory unless later adopted through a reviewed governance path.

## Change Receipt

This README now clarifies source verification for first-time visitors, explains the repository's relationship to C2PA/content authenticity, and links the v0.1 schema, example packet, boundary notes, and contribution guidance.
