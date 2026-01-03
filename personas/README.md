# Personas

This folder contains enriched contact/persona data with role labels.

## File Format

### `contacts.json`
```json
{
  "contacts": [
    {
      "contact_id": "003xxx",
      "salesforce_account_id": "001xxx",
      "name": "John Doe",
      "email": "john@company.com",
      "title": "VP of Sales",
      "department": "Sales",
      "seniority": "VP",
      "role_in_deal": "Champion",
      "linkedin_url": "https://linkedin.com/in/johndoe",
      "tenure_months": 18,
      "previous_companies": ["Company A", "Company B"],
      "enriched_date": "2025-12-01"
    }
  ]
}
```

## Role Labels

Label contacts with their role in the deal:

| Role | Description |
|------|-------------|
| **Champion** | Internal advocate who pushes for purchase |
| **Decision Maker** | Has budget authority and final sign-off |
| **Influencer** | Provides input but doesn't decide |
| **Blocker** | May oppose or slow down the deal |
| **End User** | Will use the product day-to-day |
| **Technical Evaluator** | Evaluates technical fit |

## Enrichment Process

1. **Export from CRM** - Pull all contacts associated with closed-won deals
2. **Enrich with Clay** - Add LinkedIn data, tenure, previous companies
3. **Label Roles** - Use Claude to identify roles based on transcripts:

   > "Review the transcripts for deal [ID] and identify who played each role:
   > - Who was the champion pushing internally?
   > - Who had budget authority?
   > - Who raised objections?
   > Label each contact accordingly."

## Persona Analysis

Ask Claude to identify patterns:

1. **Champion Patterns**
   > "Analyze all contacts labeled as Champions and identify:
   > - Common titles and seniority levels
   > - How long they've been at the company
   > - Previous companies (any patterns?)
   > - What motivates them based on transcripts"

2. **Buying Committee Composition**
   > "For won deals, what does the typical buying committee look like?
   > - How many people involved?
   > - What roles are represented?
   > - Who typically initiates vs. who closes?"

3. **Persona Messaging**
   > "Based on transcript analysis, what messaging resonates with each persona?
   > - What do Champions care about?
   > - What do Decision Makers need to see?
   > - What concerns do Technical Evaluators raise?"
