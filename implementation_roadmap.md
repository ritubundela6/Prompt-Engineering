# Implementation Roadmap - Apex Retail Group (Branch A)

REQ-004 / TR-003. Ratings, timings and roles are planning judgments from the dossier. Apex's budget, systems and team are unknown.

---

## 1. Prompt (Planning Prompting)

Generate a phased 12-month implementation roadmap and a risk mitigation registry for Branch A (E-Commerce & Logistics Overhaul), the selected winner. Act as a Project Manager.

1. Outline three distinct implementation phases over 12 months. Pause and write only phase names and durations.
2. Once the user says "Execute", write detailed milestones, activities and RACI assignments for each phase.
3. Identify 3 critical implementation risks in a markdown table with columns: Risk Event, Probability (Low/Med/High), Impact (Low/Med/High), Mitigation Strategy.

---

## 2. Result Part 1 - Phase Outline

| Phase | Name | Duration |
|---|---|---|
| 1 | Stabilize and Foundation | Months 1-3 |
| 2 | Build and Integrate | Months 4-8 |
| 3 | Launch, Optimize and Scale | Months 9-12 |

---

## 3. Result Part 2 - Risk Mitigation Registry (TR-003)

| Risk Event | Probability | Impact | Mitigation Strategy |
|---|---|---|---|
| Inventory system integration fails or data migration is inaccurate, so stock records stay unreliable after go-live | Med | High | Run a stock count and data clean-up before migration. Pilot in a few stores and one warehouse. Reconcile in parallel for 4-6 weeks before cutover. |
| 3PL transition disrupts fulfilment, causing delays, errors or lost visibility during the switch | Med | High | Select the 3PL against SLA and system-integration criteria. Move volume in stages. Keep the current shipping process as a fallback until the 3PL meets agreed service levels. |
| Excess stock isn't cleared, so Apex pays 3PL storage fees on slow-moving goods and carry costs stay high | High | Med | Run markdown and liquidation before the 3PL move. Set stock-clearance targets by SKU. Send only saleable inventory to the 3PL. |

---

## 4. Result Part 3 - Detailed Plan (after "Execute")

**RACI key:** R = Responsible, A = Accountable, C = Consulted, I = Informed.
**Roles:** Sponsor = executive sponsor, PM = project manager, IT = IT/ERP lead, SC = supply chain/inventory manager, Ecom = e-commerce manager, Fin = finance, 3PL = 3PL partner, Ops = store operations. Rename to match Apex's actual team.

### Phase 1: Stabilize and Foundation (Months 1-3)

**Milestones**
- M1 (Month 1): Project charter, budget and baseline KPIs approved.
- M2 (Month 2): Full stock count completed, and clearance plan approved.
- M3 (Month 3): Inventory system and 3PL vendors selected.

**Activities**
- Baseline the KPIs: margin, inventory value and turnover, conversion, abandonment and shipping time.
- Audit the current systems (ERP, POS, WMS) and the checkout funnel.
- Count stock across all warehouses and 45 stores, and classify SKUs as fast, slow or dead.
- Start markdowns and liquidation of slow stock.
- Fix quick wins on checkout, such as showing shipping costs early and adding guest checkout.
- Run the vendor RFP for the inventory system and the 3PL, scoring integration capability.

| Activity | Sponsor | PM | IT | SC | Ecom | Fin | 3PL | Ops |
|---|---|---|---|---|---|---|---|---|
| Charter, budget, KPI baseline | A | R | C | C | C | R | I | I |
| Stock count and SKU classification | I | A | C | R | I | C | I | R |
| Liquidation plan | C | A | I | R | C | R | I | C |
| Checkout quick wins | I | A | C | I | R | C | I | I |
| Vendor selection (system and 3PL) | A | R | R | R | C | C | C | I |

### Phase 2: Build and Integrate (Months 4-8)

**Milestones**
- M4 (Month 5): Inventory system configured, with clean data loaded.
- M5 (Month 6): Pilot live in a small group of stores and one warehouse.
- M6 (Month 8): Checkout redesign live, and 3PL integration tested end-to-end.

**Activities**
- Configure the inventory system for real-time stock by location, with reorder rules.
- Clean and migrate SKU, location and stock data.
- Integrate the inventory system with POS and the online store, and connect carrier and 3PL feeds.
- Run a pilot with parallel reconciliation for 4-6 weeks.
- Redesign checkout: fewer steps, more payment options and abandoned-cart recovery emails.
- Train store and warehouse staff.
- Test the 3PL with a small share of orders while keeping the current process as a fallback.

| Activity | Sponsor | PM | IT | SC | Ecom | Fin | 3PL | Ops |
|---|---|---|---|---|---|---|---|---|
| System configuration and data migration | I | A | R | R | C | I | I | C |
| POS, web and 3PL integration | I | A | R | C | R | I | R | I |
| Pilot and reconciliation | C | A | R | R | C | C | C | R |
| Checkout redesign and A/B testing | I | A | C | I | R | I | I | I |
| Staff training | I | A | C | R | C | I | C | R |

### Phase 3: Launch, Optimize and Scale (Months 9-12)

**Milestones**
- M7 (Month 9): Full rollout to all 45 stores and all warehouses.
- M8 (Month 10): 3PL carries the agreed share of online volume, with SLAs being met.
- M9 (Month 12): Post-implementation review and KPI results against baseline.

**Activities**
- Roll out in waves, with go/no-go gates after each wave.
- Shift online fulfilment to the 3PL in stages, and add ship-from-store where stock allows.
- Track weekly dashboards for inventory accuracy, shipping time, conversion and abandonment.
- Tune reorder points and markdown rules from the live data.
- Review 3PL performance against SLAs.
- Measure the margin recovery against the baseline.
- Hand over to business-as-usual support, and decide on next steps, such as a targeted store review.

| Activity | Sponsor | PM | IT | SC | Ecom | Fin | 3PL | Ops |
|---|---|---|---|---|---|---|---|---|
| Phased rollout and go/no-go gates | A | R | R | R | C | I | C | R |
| 3PL volume ramp and SLA tracking | I | A | C | R | C | I | R | I |
| KPI dashboard and tuning | I | A | R | R | R | C | I | I |
| Margin and ROI review | A | R | I | C | C | R | I | I |
| Handover to business as usual | A | R | R | R | R | I | C | C |

---

## 5. Suggested Targets (from the earlier gap analysis)

These are targets to test, not commitments.
- Conversion: about 1.7-2.0%.
- Cart abandonment: about 70-76%.
- Shipping: 2-3 days.
- Inventory: apparel turnover of 3-6x.
- Margin recovery can't be targeted until the baseline of the 15% decline is clarified.

---

## 6. Open Items

- Confirm whether the 15% margin decline is relative or percentage points.
- Obtain inventory value, COGS, days on hand and turnover.
- Confirm current systems (ERP/POS/WMS), budget and timeline.
- Replace the generic roles with named owners.
