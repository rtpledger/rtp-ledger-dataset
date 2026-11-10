# RTP Ledger open slot RTP dataset

## Summary
- **Records:** 2625 source-backed primary RTP claims with indexable slot pages
- **Evidence as of:** 2026-09-27
- **Source data modified:** 2026-09-26
- **Selection policy modified:** 2026-09-26
- **Dataset modified:** 2026-09-26
- **Fingerprint:** sha256:7eb3f4e4c17148b86ce3be1dfc6809552ba7de17b2b7a49618a8a77bb39ebadf
- **Licence:** CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/)
- **Attribution:** RTP Ledger (rtpledger.com)

## Files
- [`/data/rtpledger-slot-rtp.csv`](https://rtpledger.com/data/rtpledger-slot-rtp.csv) — flat table (one row per slot)
- [`/data/rtpledger-slot-rtp.json`](https://rtpledger.com/data/rtpledger-slot-rtp.json) — same cohort with nested source objects
- [`/data/slots-citable.json`](https://rtpledger.com/data/slots-citable.json) — identical record set used by citation tooling

## Selection
Only primary RTP claims that pass the production provenance and slot-indexing gate are included:

- source status is `official_verified` or `secondary_verified`
- checked date is present
- at least one qualifying HTTPS public source
- claim-specific evidence locator exists
- the slot detail page is indexable under the current launch policy

Excluded statuses: missing, unverified, conflict_detected, manual_review_required.

## Fields (CSV)
| Column | Meaning |
| --- | --- |
| name | Slot display name in RTP Ledger |
| slug | Stable RTP Ledger slug |
| provider | Provider display name |
| record_url | Canonical slot page |
| content_modified_at | Last material change on the slot record |
| primary_rtp_value | Primary recorded theoretical RTP (%) |
| primary_rtp_source_status | `official_verified` or `secondary_verified` |
| primary_rtp_checked_at | Check date for the primary RTP claim |
| claim_evidence_url | Claim-specific evidence page |
| source_names | Qualifying source names (` | ` separated) |
| source_types | Source types (` | ` separated) |
| source_urls | Source URLs (` | ` separated) |

## Methodology and sources
- Methodology: https://rtpledger.com/methodology
- Source policy: https://rtpledger.com/source-policy
- Corrections: https://rtpledger.com/corrections-policy
- Terms: https://rtpledger.com/terms

Primary RTP is stored separately from any recorded range. It is not necessarily the highest endpoint, and it is not a provider default, active build or casino configuration. Verify the in-game paytable before play.

Where a record cites a retained [slot.report](https://slot.report/) snapshot among field sources, attribute slot.report under CC-BY together with the RTP Ledger check date. That match is secondary corroboration, not proof of an independent upstream origin.

## Citation
RTP Ledger (rtpledger.com), source-backed slot primary RTP export (2026-09-26). Licence CC BY 4.0.

## Version
Generator version 1. Re-run `node --import tsx scripts/emit-citable-slots.ts` (also wired into `prebuild` / `predev`) to regenerate every artifact from the same selection gate. No values are invented.
