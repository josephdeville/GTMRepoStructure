# Scripts & Automation

This folder contains scripts for data processing, enrichment, and automation.

## Available Scripts

### Data Processing
- `export-crm.py` - Export and format CRM data
- `process-transcripts.py` - Process transcript exports into standard format
- `enrich-accounts.py` - Enrich account data via Clay API

### Research Automation
- `search-triggers.py` - Search for situational changes using SERP APIs
- `monitor-accounts.py` - Monitor target accounts for trigger events

### Analysis
- `segment-analysis.py` - Analyze CRM data by segment
- `campaign-metrics.py` - Calculate campaign performance metrics

## Setup

```bash
# Create virtual environment
python -m venv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows

# Install dependencies
pip install -r requirements.txt

# Configure API keys
cp .env.example .env
# Edit .env with your API keys
```

## API Integrations

| Service | Purpose | Config |
|---------|---------|--------|
| Salesforce | CRM export | SFDC_* vars |
| Clay | Enrichment | CLAY_API_KEY |
| Gong | Transcripts | GONG_* vars |
| SERP API | Trigger research | SERP_API_KEY |

## Usage with Claude Code

These scripts can be run by Claude Code to automate data processing:

> "Run the CRM export script and save the results to the crm folder"

> "Use the search triggers script to find recent funding announcements for accounts in target-accounts.json"

> "Process the new transcript export and add it to the transcripts folder"

## Notes

- Scripts are designed to output standard JSON formats
- All outputs should be committed to the repo
- Run enrichment scripts periodically (monthly) to keep data fresh
