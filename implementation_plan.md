# HubSpot Implementation Plan

## Roadmap prompt

```text
Act as an enterprise CRM implementation lead. Produce a six-month HubSpot Sales Hub implementation plan for Apex Cloud Services and 150 representatives moving from fragmented offline spreadsheets. Use Phase 1 Planning & Data Cleanup in Month 1, Phase 2 System Configuration & Pilot in Months 2–3, Phase 3 Full Migration & Staff Training in Months 4–5, and Phase 4 Post-Launch Optimization in Month 6. Provide a Markdown text Gantt, proposed owners, deliverables, measurable exit gates, dependencies, and rollback approach. Treat thresholds as proposed targets, not commitments. Confirm edition and licensing fit before configuration. Map to REQ-004.
```

## Six-month Markdown Gantt

X = active phase. Months are relative; no calendar start date was supplied.

| Phase | M1 | M2 | M3 | M4 | M5 | M6 |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| Planning & Data Cleanup | X | — | — | — | — | — |
| System Configuration & Pilot | — | X | X | — | — | — |
| Full Migration & Staff Training | — | — | — | X | X | — |
| Post-Launch Optimization | — | — | — | — | — | X |

## Deliverables and proposed gates

| Phase | Proposed owners | Activities and deliverables | Proposed exit gate |
|---|---|---|---|
| Month 1 | Project manager, sales operations, data stewards | Inventory all spreadsheets; establish a source of truth; map accounts, contacts, deals and owners; standardize fields; deduplicate; verify edition, seats and written quote; approve success metrics | All identified sources catalogued; mapping and budget approved; at least 98% required-field completeness in the approved migration dataset |
| Months 2–3 | CRM administrator, implementation partner, sales champions | Configure pipeline, roles, permissions, fields and dashboards; test only required integrations; run trial imports and a proposed 15-rep pilot | All critical UAT cases pass; no unresolved critical defects; business owner signs off pilot and migration reconciliation |
| Months 4–5 | Migration lead, trainers, sales managers | Train and migrate remaining 135 reps in controlled waves; perform final delta migration; reconcile counts, key values, relationships and ownership; activate support and cutover controls | All 150 reps provisioned and trained; all in-scope records reconciled or covered by approved exceptions; at least 90% weekly active use for two consecutive weeks |
| Month 6 | Sales operations, administrator, support lead | Resolve support issues; optimize reports and workflows; review usage and data quality; transfer documentation and support ownership | Support handover signed; critical issue backlog cleared; KPI baseline and optimization backlog accepted |

All thresholds and pilot sizes are proposed planning targets requiring sponsor approval, not observed performance or vendor guarantees.

## Dependencies and rollback

Data cleanup and approved mapping precede pilot imports. Pilot sign-off precedes migration waves. Confirm feature entitlements before configuration; do not assume Professional includes Enterprise-only features such as custom objects.
Back up source spreadsheets and approved export snapshots before migration. Freeze uncontrolled spreadsheet edits during final cutover. Test rollback before production go-live. If a wave fails critical reconciliation or UAT, stop later waves, retain the approved source snapshot, and reconcile any CRM-only changes before reverting to a controlled source workflow. Resume only after business-owner approval.

## Risk registry prompt

```text
Create exactly three implementation risks for the Apex Cloud Services HubSpot rollout. Use columns Risk Event, Probability, Impact, and Mitigation. Cover fragmented-data migration, adoption resistance, and edition/integration/cost mismatch. Use qualitative probability estimates, not invented statistics. Make mitigations actionable and label estimates as planning assumptions.
```

## Risk registry

Probability and impact are qualitative planning judgments, not statistically measured forecasts.

| Risk Event | Probability | Impact | Mitigation |
|---|---|---|---|
| Fragmented spreadsheets cause duplicate, incomplete, or incorrectly linked migrated records | High | High: unreliable client history, reporting errors, and delayed cutover | Data stewards define mapping and deduplication rules; validate trial imports; reconcile counts and relationships; retain snapshots; require sign-off before each wave |
| Sales representatives continue using spreadsheets instead of the CRM | Medium | High: low adoption and incomplete pipeline visibility | Sales managers appoint champions; run the 15-rep pilot; provide role-specific practice; track weekly usage; coach low-use teams; restrict uncontrolled spreadsheet workflows after approved cutover |
| Required features, seats, or integrations exceed the quoted edition or budget | Medium | High: additional licensing costs, redesign, or rollout delays | Procurement and CRM lead confirm 150 full sales seats, edition entitlements, billing terms and onboarding; test essential integrations during pilot; require change control and a written quote before commitment |
