# Campaigns

This folder contains all unique campaigns. Each campaign targets a specific segment with tailored messaging based on situational changes.

## Folder Structure

```
campaigns/
├── README.md
├── _template/                    # Template for new campaigns
│   ├── campaign-brief.md
│   ├── target-accounts.json
│   ├── messaging.md
│   └── results.md
├── 2025-q4-series-a-saas/       # Example campaign
│   ├── campaign-brief.md
│   ├── target-accounts.json
│   ├── messaging.md
│   ├── research/
│   │   └── situational-changes.md
│   └── results.md
└── 2025-q4-enterprise-finserv/  # Another campaign
    └── ...
```

## Creating a New Campaign

1. **Copy the template folder:**
   ```bash
   cp -r _template/ YYYY-QQ-campaign-name/
   ```

2. **Define the campaign brief** - Fill out `campaign-brief.md`

3. **Pull relevant data:**
   > "Query the master data and pull in all existing customers that match this campaign's segment. Also pull relevant transcripts for analysis."

4. **Research situational changes:**
   > "Based on our ICP and closed-won deals in this segment, what are the situational changes that typically drive purchase? Use search tools to identify these signals for our target accounts."

5. **Develop messaging** - Based on research, create targeted messaging

6. **Track results** - Update `results.md` as campaign runs

## Compound Learning

Each campaign should:
- Reference learnings from previous campaigns
- Contribute new learnings back to `/learnings`
- Update hypotheses based on results

When starting a campaign, ask Claude:
> "Review the learnings folder and previous campaigns targeting similar segments. What hypotheses should we test? What messaging has worked before?"
