# Data dictionary — source tables

Source: Analytics Engineering, Marketing Campaigns & Conversions Dataset, v1.0.0. CC BY 4.0. Synthetic educational data.

## campaigns.csv — one row per campaign
- `campaign_id`: stable campaign key
- `campaign_name`: campaign display name
- `channel`: paid media channel
- `objective`: campaign objective (awareness, lead_gen, acquisition)
- `start_date`, `end_date`: active dates
- `budget`: planned budget (USD)

## daily_spend.csv — one row per campaign and active date
- `spend_id`: stable delivery-row key
- `campaign_id`: campaign foreign key
- `spend_date`: delivery date
- `impressions`, `clicks`: recorded ad delivery and clicks
- `spend`: media cost (USD)

## leads.csv — one row per lead
- `lead_id`: stable lead key
- `campaign_id`: credited campaign (last-touch assignment)
- `created_at`: lead creation date
- `lead_source`: credited source channel
- `lead_score`: qualification score (1–100)

## conversions.csv — one row per converted lead
- `conversion_id`: stable conversion key
- `lead_id`: converted-lead foreign key
- `converted_at`: conversion date
- `conversion_type`: trial or purchase
- `revenue`: attributed revenue (USD)

The source has one assigned campaign per lead; multi-touch journeys are not supplied.
