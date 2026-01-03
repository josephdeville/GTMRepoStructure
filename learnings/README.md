# Learnings & Hypotheses

This folder contains compound learnings that accumulate over time as you run campaigns. This is where knowledge compounds - every new campaign takes in these learnings and contributes back.

## Purpose

Unlike Clay tables that exist in isolation, this repo structure allows learnings to compound:
- Each campaign references existing hypotheses
- Each campaign validates or invalidates hypotheses
- New insights are added back to the master files
- The model gets better with each iteration

## Files

### `hypotheses.md`
Master list of hypotheses about what works for your GTM motion.

### `segment-insights.md`
Deep insights about each customer segment.

### `situational-changes.md`
Catalog of business changes that signal buying intent.

## Updating Learnings

After each campaign:

1. **Review results** from the campaign
2. **Update hypotheses** - mark as validated/invalidated
3. **Add new hypotheses** discovered during the campaign
4. **Update segment insights** with new information
5. **Document new situational changes** identified

Ask Claude:
> "Review the results from campaign [X] and update our learnings files:
> - Which hypotheses were validated?
> - Which were invalidated?
> - What new hypotheses should we add?
> - What new segment insights did we learn?"
