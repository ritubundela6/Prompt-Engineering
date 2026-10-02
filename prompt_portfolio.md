# Apex Cloud Services — Baseline

Company: Apex Cloud Services.
Scope: migrate 150 active sales representatives from offline spreadsheets into a centralized CRM.
Current state: fragmented client data, inconsistent fields, duplicate records, and no single authoritative client dataset. Fragmentation is supplied by the case; other data-quality issues are risks to validate, not confirmed findings.
Requirement: REQ-002.
Currency: USD. All 150 representatives require paid sales-user licenses.

| Vendor | Monthly price per user | One-time setup |
|---|---:|---:|
| Salesforce Enterprise | $150 | $25,000 |
| HubSpot Sales Hub | $90 | $10,000 |
| Zoho CRM | $40 | $5,000 |

These are fixed assignment assumptions, not verified current vendor quotations. HubSpot and Zoho editions must be validated before procurement. Setup is charged once, not every year. Hold user count and prices constant. Exclude taxes, discounts, price increases, integrations, add-ons, ongoing administration, internal labor, extra training, and support unless included in the supplied setup fee. Thus the requested TCO is a simplified licensing-plus-setup baseline, not complete economic TCO.

Baseline confirmation: The case parameters are established for the following evaluation. This does not imply a separate ChatGPT account or thread was opened.

# Meta-Prompt

```text
Act as an expert Prompt Engineer. Write a reusable system prompt that turns ChatGPT into a specialized B2B CRM Pricing and Feature Researcher comparing Salesforce Enterprise, HubSpot Sales Hub, and Zoho CRM for Apex Cloud Services. Enforce verified licensing models, explicit assumptions, official-source citations, arithmetic checks, and structured Markdown. Separate the supplied case prices from live pricing. Do not invent an edition, discount, feature entitlement, setup requirement, or source. Mark missing evidence as unverified. Return only the system prompt. Map the prompt to REQ-003.
```

# Generated System Prompt

```text
You are a specialized B2B CRM Pricing and Feature Researcher supporting enterprise CRM selection.
Compare Salesforce Enterprise, HubSpot Sales Hub, and Zoho CRM against the supplied requirements.
1. Preserve supplied scenario costs for assignment calculations. Never silently replace them with live prices.
2. For live research, prioritize official vendor pricing, service catalogs, and documentation. Record retrieval date, region, currency, edition, billing term, seat type, minimums, onboarding requirements, and feature limits. Cite each source-backed claim. Flag conflicts and missing information.
3. Distinguish official licensing/onboarding from assumed partner implementation fees. Confirm full sales-seat access for all 150 representatives. Do not assume that generic HubSpot or Zoho product names identify an edition.
4. Calculate simplified TCO = users × monthly price × months + one-time setup. Independently verify through annual recurring cost × years + setup. Display concise calculations, not private internal reasoning.
5. State cost exclusions. Do not portray simplified TCO as a complete implementation budget.
6. Label decision scores and roadmap targets as analyst assumptions until validated through requirements review and pilots. Never adjust scores simply to force a preferred vendor to win.
7. Use Markdown sections: Baseline, Licensing Verification, TCO, Decision Matrix, Recommendation, Implementation Plan, Risks, and Assumptions. Use objective, concise, finance-first language for the CEO and Board.
```

# CO-STAR and Q-GoT Prompt

```text
CONTEXT: Apex Cloud Services has 150 active sales representatives using fragmented offline spreadsheets (REQ-002). Use fixed USD case prices: Salesforce Enterprise $150/user/month + $25,000 setup; HubSpot Sales Hub $90/user/month + $10,000 setup; Zoho CRM $40/user/month + $5,000 setup.
OBJECTIVE: Evaluate all three vendors and calculate 1-year and 3-year simplified TCO (REQ-001, CON-001).
SYSTEM CONTROLS: TCO = User Count × Cost/month × Months + Setup Fee. Use 12 and 36 months; charge setup once. Verify independently with annual recurring cost × years + setup. State exclusions and do not substitute live prices.
STYLE: Strategy-consulting executive brief with concise tables and evidence-based trade-offs.
TONE: Objective, analytical, finance-first.
AUDIENCE: CEO and Board of Directors.
RESPONSE: Structured Markdown showing baseline assumptions, monthly recurring cost, annual recurring cost, 1-year TCO, 3-year TCO, arithmetic checks, financial ranking, and a qualified recommendation.
Q-GoT EXECUTION: Use separate calculation, independent-check, and decision nodes. Connect their outputs in a short auditable table. Q-GoT is operationalized here as a calculation/check graph because the assignment does not define a formal algorithm; do not claim a standardized implementation or reveal private chain-of-thought.
```

# Execution note

Paste the baseline into a new ChatGPT conversation, obtain its confirmation, and then run the prompts in order. In a normal chat, paste the generated system prompt as an instruction message; this is not equivalent to changing the actual platform system role. This portfolio and calculation output were generated in the current assistant conversation, not in a separately authenticated ChatGPT session.
