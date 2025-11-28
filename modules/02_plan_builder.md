> Refined Module 02 based on AI critique: added an input/output contract section, a standardized cost estimation schema and contingency/fallback policies.
# Module: Plan Builder

## Purpose
The Plan Builder module constructs a **draft itinerary** based on normalized inputs from the Intake module. It organizes trip days into time blocks, allocates activities, lodging, meals, and transit, and attaches assumptions with confidence levels. The output is passed to the Feasibility Guardrails module for validation before rendering.

---

## Input/Output Contract

### Inputs (from Intake)
- **Trip Dates**: normalized start and end dates
- **Origin/Destination**: city, region, or country
- **Party Details**: size, ages, accessibility needs
- **Budget Schema**: total, per-day, per-person, shared costs
- **Preferences**: pace (relaxed/packed), activity types, dietary constraints, accessibility requirements
- **Constraints**: time limits, must-see items, exclusions

### Outputs (to Feasibility Guardrails)
- **Daily Schedule Blocks**: morning, afternoon, evening
- **Activities**: with start/end times, estimated durations
- **Transit Segments**: mode, duration, buffer assumptions
- **Lodging Choices**: per-night cost, location notes
- **Meals**: dietary alignment, estimated costs
- **Cost Estimates**: per-item, per-day, total trip
- **Assumptions**: labeled with confidence (high/medium/low)
- **Flags**: budget risk, time risk, weather dependency, accessibility gaps, data gaps

---

## Workflow Steps
1. **Read Intake Payload**: normalize trip data and preferences.
2. **Derive Trip Structure**: split into days and time blocks.
3. **Allocate Core Elements**: lodging, transit, activities, meals.
4. **Estimate Costs**: apply standardized schema (see below).
5. **Insert Buffers**: transit delays, check-in/out, peak traffic.
6. **Attach Assumptions**: document reasoning and confidence.
7. **Package Outputs**: structured draft itinerary with flags for Guardrails.

---

## Standardized Cost Estimation Schema

Each cost entry must include:
- **Category**: lodging, transit, activity, meal, misc.
- **Type**: shared vs. per-person
- **Currency**: normalized to intake currency
- **Estimate**: numeric value
- **Confidence**: high/medium/low
- **Notes**: source or assumption

### Example
```yaml
- category: lodging
  type: shared
  currency: USD
  estimate: 120
  confidence: high
  notes: "Average mid-range hotel in downtown area"
