# RuntimeVendor Watchlist v0.1

**Status: CANDIDATE — DO NOT ADOPT YET**

Issue: hummbl-dev/ai-source-verification#13
Parent issue: hummbl-dev/ai-source-verification#9

## Context

The architecture map identifies `RuntimeVendor` as a candidate primitive. Source claims reference Prime Intellect, and the broader ecosystem includes OpenAI GPT-Live, Anthropic, and local NIM deployments. Host-level controls, contracts, and trust boundaries are not yet established.

## Scope

Draft a candidate `RuntimeVendor Watchlist v0.1` that includes:

- **Vendor entries**: Prime Intellect, OpenAI GPT-Live, Anthropic, local NIM
- **Governance posture per vendor**: `DO_NOT_ADOPT_YET`, `SOURCE_CLAIM`, etc.
- **Trust boundary definition**: data residency, access level, contract requirements
- **Hosted vs local execution boundary**
- **Data handling requirements per vendor**
- **Vendor disclosure template**: what must be disclosed before adoption

## Candidate vendor entries

### Prime Intellect

- **Posture**: `DO_NOT_ADOPT_YET` / `SOURCE_CLAIM`
- **Trust boundary**: data residency TBD, access level TBD
- **Hosted/local**: both claimed
- **Local audit**: `LOCAL_AUDIT_REQUIRED`

### OpenAI GPT-Live

- **Posture**: `DO_NOT_ADOPT_YET` / `SOURCE_CLAIM`
- **Trust boundary**: hosted, data residency per OpenAI policy
- **Hosted/local**: hosted
- **Local audit**: `LOCAL_AUDIT_REQUIRED`

### Anthropic

- **Posture**: `DO_NOT_ADOPT_YET` / `SOURCE_CLAIM`
- **Trust boundary**: hosted, data residency per Anthropic policy
- **Hosted/local**: hosted
- **Local audit**: `LOCAL_AUDIT_REQUIRED`

### Local NIM

- **Posture**: `DO_NOT_ADOPT_YET` / `SOURCE_CLAIM`
- **Trust boundary**: local, data residency local
- **Hosted/local**: local
- **Local audit**: `LOCAL_AUDIT_REQUIRED`

## Vendor disclosure template

```yaml
vendor_id:
vendor_name:
governance_posture:
trust_boundary:
  data_residency:
  access_level:
  contract_requirements:
hosted_vs_local:
data_handling:
  allowed_data:
  prohibited_data:
  retention_policy:
disclosure_required:
  - capability_claims
  - data_handling_practices
  - security_posture
  - pricing_model
  - sla_terms
local_audit_status:
```

## Acceptance criteria

- [x] Watchlist documented with 4 vendor entries
- [x] Governance posture per vendor documented
- [x] Trust boundary template documented
- [x] Vendor disclosure template documented
- [ ] Watchlist document in `docs/`
- [ ] Vendor entries with posture labels for all 4 named vendors
- [ ] Trust boundary schema or template
- [ ] All entries marked `candidate` / `DO_NOT_ADOPT_YET`
- [ ] No vendor commitment or dependency adoption
- [ ] Explicit `LOCAL_AUDIT_REQUIRED` where local feasibility is unverified

## Non-goals

- No vendor commitment or contract
- No dependency adoption
- No canonization as HUMMBL/BaseN/Ownward standard
- No operator credential use

## Related

- `hummbl-dev/ai-source-verification#9` — parent issue
- `hummbl-dev/ai-source-verification#12` — Ownward Voice Runtime boundary (sibling)

## Fact posture

Derived from issue #13 and Prime Intellect architecture map. Watchlist is candidate only. No vendor commitments. All entries require local audit.

## Receipt

- **Issue**: hummbl-dev/ai-source-verification#13
- **Vendor entries**: 4 (Prime Intellect, OpenAI GPT-Live, Anthropic, local NIM)
- **Disclosure template fields**: 10+
- **Review status**: PENDING
