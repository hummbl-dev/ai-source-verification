# AI Source Verification

AI Source Verification is a public seed repository for source verification for AI-mediated work.

## Purpose

Source, citation, provenance, and claim-verification patterns for AI-mediated work.

In this repository, source verification means recording enough evidence for a
reader or reviewer to trace an AI-mediated claim back to the sources it depends
on. The goal is not to prove that every claim is true automatically. The goal is
to make citation, provenance, and verification status explicit enough for human
review.

## Relationship To Content Authenticity

Content authenticity systems such as C2PA focus on provenance signals for media
and generated content. This repository is adjacent to that space: it focuses on
source and claim evidence packets that can be used alongside content
authenticity metadata.

The v0.1 packet posture here is exploratory. It does not define a universal
content authenticity standard, replace C2PA, or certify that a claim is correct.
It provides candidate structures for recording source references, evidence
status, and verification boundaries.

## Status

Early public seed repository. Candidate namespace only.

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

## Repository Map

- `schemas/` contains candidate JSON schemas for verification packets.
- `examples/` contains public-safe example packets.
- `fixtures/` is reserved for test fixtures.
- `docs/` is reserved for explanatory documentation.
- `receipts/` is reserved for change or review receipts.

## Receipt

- Clarified what source verification means for a first-time visitor.
- Explained the relationship to content authenticity and C2PA-style provenance without claiming replacement or canon status.
- Made schemas and examples discoverable from the README.
