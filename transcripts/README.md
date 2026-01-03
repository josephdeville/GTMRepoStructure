# Call Transcripts

This folder contains all sales call transcripts exported from Gong, Chorus, or similar tools.

## File Format

Store transcripts as JSON with a join identifier (Salesforce ID) to link to CRM data.

### `transcripts.json`
```json
{
  "transcripts": [
    {
      "transcript_id": "gong_123456",
      "salesforce_opportunity_id": "006xxx",
      "salesforce_account_id": "001xxx",
      "call_date": "2025-05-20T14:30:00Z",
      "call_type": "Discovery",
      "duration_minutes": 32,
      "participants": [
        {
          "name": "Jane Smith",
          "role": "Account Executive",
          "type": "internal"
        },
        {
          "name": "John Doe",
          "title": "VP of Sales",
          "company": "Acme Corp",
          "type": "external",
          "contact_id": "003xxx"
        }
      ],
      "transcript": "Full transcript text here...",
      "summary": "AI-generated summary of the call",
      "key_topics": ["pricing", "integration", "timeline"],
      "next_steps": ["Send proposal", "Schedule technical demo"],
      "sentiment": "positive"
    }
  ]
}
```

## Export Process

### From Gong
1. Use Clay's Gong integration to export transcripts
2. Include the Salesforce Opportunity ID for linking
3. Export as JSON format

### From Chorus
1. Use API to export transcripts with deal IDs
2. Map to Salesforce IDs
3. Convert to JSON format

## Analysis Prompts

Once transcripts are loaded, ask Claude to:

1. **Segment Analysis**
   > "For each customer segment in our ICP, read the transcripts and identify:
   > - Common pain points mentioned
   > - Situational changes that drove the purchase
   > - Objections raised and how they were overcome
   > - Key phrases that indicate buying intent"

2. **Champion Identification**
   > "Analyze these transcripts and identify patterns in champion behavior:
   > - What questions do champions ask?
   > - How do they describe the problem internally?
   > - What motivates them to push for purchase?"

3. **Competitive Intelligence**
   > "Review transcripts for mentions of competitors and summarize:
   > - Which competitors come up most often
   > - Why prospects considered alternatives
   > - What made them choose us over competitors"

## Linking Data

Transcripts should be linked to:
- **Deals** via `salesforce_opportunity_id`
- **Accounts** via `salesforce_account_id`
- **Contacts/Personas** via `contact_id`

This allows Claude to cross-reference transcript insights with deal outcomes and customer characteristics.
