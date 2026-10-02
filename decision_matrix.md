# Weighted Decision Matrix

## Prompt

```text
Create a Markdown weighted decision matrix for Apex Cloud Services using TCO Cost Model 30%, Customization & Scale 20%, Setup Speed 25%, User Adoption Ease 25%. Verify weights sum to 1.0. Use 1–10 raw scores, with 10 best, and calculate Weighted Score = Raw Score × Weight. Derive cost scores from explicit three-year TCO bands: at most $200,000 = 10; above $200,000 through $550,000 = 7; above $550,000 = 3. For this illustrative exercise use customization/speed/adoption scores Salesforce 10/5/6, HubSpot 8/9/9, Zoho 7/7/8. These are unvalidated analyst judgments, not measured vendor performance. Show every contribution, totals, ranking, rationale, and sensitivity. Do not imply HubSpot must win because the roadmap names it. Map to TR-002.
```

## Scoring controls

Weights: 0.30 + 0.20 + 0.25 + 0.25 = 1.00 (100%). Higher scores are better; maximum weighted total is 10.00.
Cost scores use illustrative three-year TCO bands: ≤ $200,000 = 10; > $200,000 and ≤ $550,000 = 7; > $550,000 = 3. This coarse rubric is an assumption, not a standard financial model.
Non-cost scores are illustrative hypotheses for pilot validation, not verified comparative facts. HubSpot is specified by the exercise for planning; its selection remains conditional.

| Criterion | Weight | Salesforce raw × weight | HubSpot raw × weight | Zoho raw × weight |
|---|---:|---:|---:|---:|
| TCO Cost Model | 30% | 3 × 0.30 = 0.90 | 7 × 0.30 = 2.10 | 10 × 0.30 = 3.00 |
| Customization & Scale | 20% | 10 × 0.20 = 2.00 | 8 × 0.20 = 1.60 | 7 × 0.20 = 1.40 |
| Setup Speed | 25% | 5 × 0.25 = 1.25 | 9 × 0.25 = 2.25 | 7 × 0.25 = 1.75 |
| User Adoption Ease | 25% | 6 × 0.25 = 1.50 | 9 × 0.25 = 2.25 | 8 × 0.25 = 2.00 |
| Total | 100% | 5.65 | 8.20 | 8.15 |

## Interpretation and sensitivity

Ranking: HubSpot 8.25, Zoho 8.15, Salesforce 5.70.
The illustrative rubric assumes Salesforce offers the strongest customization fit but needs more setup and training; HubSpot best fits rapid rollout and adoption; Zoho balances lower cost with moderate implementation effort. These judgments require trial evidence, reference checks, and edition validation.
HubSpot's 0.10-point lead is fragile. Reducing its adoption score from 9 to 8 reduces its total to 8.00, placing Zoho first. Moving only 2 percentage points of weight from adoption to cost produces a tie: HubSpot 8.21 and Zoho 8.21. Therefore HubSpot is not a robust winner.
Do not approve its $275,000 three-year premium over Zoho without validating user adoption, implementation effort, required features, and economic benefits. No ROI benefit has been demonstrated by the assignment.
