# Verified TCO Output

Formula: TCO = 150 × monthly price × months + setup.

| Vendor | Monthly recurring | Annual recurring | 1-year TCO | 3-year TCO |
|---|---:|---:|---:|---:|
| Salesforce | $22,500 | $270,000 | $295,000 | $835,000 |
| HubSpot | $13,500 | $162,000 | $172,000 | $496,000 |
| Zoho | $6,000 | $72,000 | $77,000 | $221,000 |

## Arithmetic checks

- Salesforce: 1 year = 150 × 150 × 12 + 25,000 = $295,000; 3 years = 150 × 150 × 36 + 25,000 = $835,000. Independent check: $270,000 × 3 + $25,000 = $835,000.
- HubSpot: 1 year = 150 × 90 × 12 + 10,000 = $172,000; 3 years = 150 × 90 × 36 + 10,000 = $496,000. Independent check: $162,000 × 3 + $10,000 = $496,000.
- Zoho: 1 year = 150 × 40 × 12 + 5,000 = $77,000; 3 years = 150 × 40 × 36 + 5,000 = $221,000. Independent check: $72,000 × 3 + $5,000 = $221,000.

## Financial finding

Zoho is the lowest-cost option. HubSpot costs $91,000 more in year one and $275,000 more over three years than Zoho. HubSpot saves $123,000 in year one and $339,000 over three years versus Salesforce.
Recommend Zoho on price alone. HubSpot is the assignment-designated implementation candidate and is conditionally preferred by the illustrative multi-criteria matrix, not by TCO alone. Validate whether usability and implementation advantages justify the premium.

## Official-source verification notes

Research date: October 2, 2026. These notes do not change case calculations.
- Salesforce official Sales pricing describes per-user/month licensing and edition-dependent features: https://www.salesforce.com/sales/pricing/
- HubSpot's official catalog lists Sales Hub Professional starting at $100/month/seat and $1,500 required onboarding; Enterprise starts at $150/month/seat, billed annually, and $3,500 onboarding: https://legal.hubspot.com/hubspot-product-and-services-catalog
- HubSpot's official sales page identifies custom objects as an Enterprise capability: https://www.hubspot.com/products/sales
- An official HubSpot blog reports Professional at $90/seat/month with annual billing, differing from the catalog's displayed starting price: https://blog.hubspot.com/sales/hubspot-sales-hub-pricing
- Zoho's official pricing result was region-localized to INR. It does not verify the case's USD $40 price or identify the required edition: https://www.zoho.com/en-us/crm/zohocrm-pricing.html

The supplied $10,000 HubSpot setup fee is a case implementation allowance, not an assertion about mandatory vendor onboarding. Resolve HubSpot pricing conflicts with a written quote and confirm editions, seats, billing terms, region, and feature entitlements before purchasing. Current Salesforce Enterprise's exact price and Zoho's USD edition price were not established by this research.
