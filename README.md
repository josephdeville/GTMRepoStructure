# GTM Engineering System

A structured repository for Go-To-Market (GTM) engineering with Claude Code. This structure enables compound learning - every campaign builds on previous learnings, and knowledge accumulates over time.

## Why This Structure?

Unlike Clay tables that exist in isolation, this repo structure allows your GTM knowledge to compound:

- **Learnings accumulate** - Each campaign contributes insights back to the master files
- **Context is preserved** - All historical data, transcripts, and insights in one place
- **Team collaboration** - Everyone can contribute via Git
- **AI-native workflow** - Designed to work seamlessly with Claude Code

## Repository Structure

```
gtm-engineering/
├── README.md                    # This file
├── icp/                         # Ideal Customer Profile
│   └── icp-definition.md        # ICP documentation
├── crm/                         # CRM Data Exports
│   ├── README.md
│   ├── deals.json               # Deal/opportunity data with ARR
│   └── accounts.json            # Enriched account data
├── transcripts/                 # Call Transcripts
│   ├── README.md
│   └── transcripts.json         # All transcripts (from Gong, etc.)
├── personas/                    # Contact & Persona Data
│   ├── README.md
│   └── contacts.json            # Enriched contacts with role labels
├── campaigns/                   # Campaign Folders
│   ├── README.md
│   ├── _template/               # Template for new campaigns
│   │   ├── campaign-brief.md
│   │   ├── messaging.md
│   │   ├── target-accounts.json
│   │   └── results.md
│   └── [campaign-folders]/      # Individual campaigns
├── learnings/                   # Compound Learnings
│   ├── README.md
│   ├── hypotheses.md            # Validated/invalidated hypotheses
│   ├── segment-insights.md      # Deep segment knowledge
│   └── situational-changes.md   # Buying trigger catalog
├── founder-notes/               # Qualitative Insights
│   ├── README.md
│   └── [dated-notes].md         # Market updates, competitive intel
└── scripts/                     # Automation Scripts
    ├── README.md
    ├── requirements.txt
    └── .env.example
```

## Getting Started

### 1. Populate Your Data

**ICP Definition**
Edit `icp/icp-definition.md` with your ideal customer profile.

**CRM Export**
Export deals and accounts from your CRM. Use Clay to enrich with current data:
- Industry
- Headcount
- Funding information
- Technologies used

Save to `crm/deals.json` and `crm/accounts.json`.

**Transcripts**
Export call transcripts from Gong/Chorus with Salesforce IDs for linking.
Save to `transcripts/transcripts.json`.

**Personas**
Export contacts and enrich with Clay. Label roles (Champion, Decision Maker, etc.).
Save to `personas/contacts.json`.

### 2. Initial Analysis

Ask Claude Code to analyze your data:

```
Review my ICP, CRM data, and transcripts. Help me understand:
1. Who are my best customer segments by ARR?
2. What patterns exist in how they buy?
3. What situational changes triggered their purchase?
4. Segment by industry, headcount, and buying behavior.
```

### 3. Generate Hypotheses

```
Based on the analysis, generate hypotheses about:
1. Which segments should we prioritize?
2. What messaging will resonate with each segment?
3. What triggers should we monitor for outreach timing?

Save these to the learnings folder.
```

### 4. Run Campaigns

Create a new campaign:
```bash
cp -r campaigns/_template campaigns/YYYY-QQ-campaign-name
```

Then ask Claude:
```
I'm starting a new campaign targeting [segment].
1. Query existing customers matching this segment
2. Pull relevant transcripts for analysis
3. Research situational changes for our target accounts
4. Develop messaging based on what's worked before
5. Create the target account list
```

### 5. Capture Learnings

After each campaign:
```
Review the results from campaign [X] and update our learnings:
1. Which hypotheses were validated/invalidated?
2. What new insights did we discover?
3. Update segment insights with new information
4. Document any new situational changes identified
```

## Key Workflows

### Segment Analysis
```
Analyze my CRM data and transcripts by segment.
For each segment (Enterprise, Mid-Market, SMB):
- What are the common pain points?
- What triggers the purchase?
- What does the buying committee look like?
- What messaging resonates?
```

### Trigger Research
```
For the accounts in [campaign]/target-accounts.json:
- Search for recent funding announcements
- Look for leadership changes
- Find expansion news
- Identify any publicly visible changes that indicate buying intent
```

### Transcript Mining
```
Review transcripts from closed-won deals in [segment] and identify:
- Key phrases that indicate buying intent
- Common objections and how they were overcome
- What champions say to sell internally
- Competitive mentions and how we compared
```

### Messaging Development
```
Based on learnings for [segment], develop messaging that:
- Addresses their specific pain points
- References relevant situational changes
- Uses language from successful transcripts
- Includes proof points from similar customers
```

## Compound Learning Loop

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│    ┌──────────┐    ┌──────────┐    ┌──────────────┐        │
│    │   Data   │───▶│ Analysis │───▶│  Hypotheses  │        │
│    └──────────┘    └──────────┘    └──────────────┘        │
│         ▲                                   │               │
│         │                                   ▼               │
│    ┌──────────┐    ┌──────────┐    ┌──────────────┐        │
│    │ Updated  │◀───│ Learnings│◀───│   Campaign   │        │
│    │   Data   │    │ Captured │    │   Executed   │        │
│    └──────────┘    └──────────┘    └──────────────┘        │
│                                                             │
│              Knowledge Compounds Over Time                  │
└─────────────────────────────────────────────────────────────┘
```

## Tools Integration

| Tool | Purpose | Folder |
|------|---------|--------|
| **Salesforce** | CRM data export | `/crm` |
| **Clay** | Data enrichment | `/crm`, `/personas` |
| **Gong/Chorus** | Transcript export | `/transcripts` |
| **SERP API / OpenWebNinja** | Trigger research | Campaign research |
| **Claude Code** | Analysis & execution | Everywhere |

## Contributing

1. Keep data files in standard JSON format
2. Update learnings after each campaign
3. Document new hypotheses and their outcomes
4. Commit regularly to preserve history

## Resources

- See `/campaigns/_template` for campaign templates
- See individual folder READMEs for detailed instructions
- Check `/learnings` for accumulated knowledge
