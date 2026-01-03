# CRM Data

This folder contains exports from your CRM with historical deal data.

## Required Files

### `deals.json`
Export of all deals/opportunities with the following fields:

```json
{
  "deals": [
    {
      "salesforce_id": "006xxx",
      "account_name": "Company Name",
      "account_id": "001xxx",
      "deal_name": "Opportunity Name",
      "stage": "Closed Won",
      "close_date": "2025-06-15",
      "arr": 50000,
      "historical_arr": [
        {"date": "2024-06-15", "arr": 25000},
        {"date": "2025-06-15", "arr": 50000}
      ],
      "industry": "SaaS",
      "headcount": 250,
      "segment": "Mid-Market",
      "champion_contact_id": "003xxx",
      "products": ["Product A", "Product B"],
      "deal_source": "Outbound",
      "sales_cycle_days": 45,
      "created_date": "2025-05-01"
    }
  ]
}
```

### `accounts.json`
Enriched account data (use Clay to enrich with current data):

```json
{
  "accounts": [
    {
      "account_id": "001xxx",
      "name": "Company Name",
      "domain": "company.com",
      "industry": "SaaS",
      "sub_industry": "Sales Tech",
      "headcount": 250,
      "headcount_range": "201-500",
      "revenue_estimate": 25000000,
      "funding_stage": "Series B",
      "total_funding": 50000000,
      "last_funding_date": "2024-03-15",
      "technologies": ["Salesforce", "Outreach", "Gong"],
      "location": {
        "city": "San Francisco",
        "state": "CA",
        "country": "US"
      },
      "linkedin_url": "https://linkedin.com/company/xxx",
      "enriched_date": "2025-12-01"
    }
  ]
}
```

## Data Enrichment Process

1. **Export from CRM** - Pull all closed-won deals with ARR data
2. **Enrich with Clay** - Add current industry, headcount, technographics
3. **Link Transcripts** - Match deals to call transcripts via Salesforce ID
4. **Update Regularly** - Re-export monthly to capture new deals

## Segmentation

After loading data, ask Claude to segment by:
- Industry
- Headcount (SMB / Mid-Market / Enterprise)
- How they buy (self-serve, sales-assisted, enterprise procurement)
- Problem sets they have

## Key Metrics to Track

- ARR by segment
- Win rates by segment
- Sales cycle length by segment
- Deal source effectiveness
- Expansion revenue patterns
