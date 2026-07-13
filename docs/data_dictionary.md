# Data dictionary

## `data/road_assets_public.csv`

| Column | Description |
|---|---|
| `asset_id` | Public synthetic road asset identifier assigned after shuffling |
| `condition_index` | Current road condition index on a 0-100 scale |
| `cost_preservation` | Cost of road action 1 |
| `cost_rehabilitation` | Cost of road action 2 |
| `cost_reconstruction` | Cost of road action 3 |
| `risk_weight` | Relative asset weight used for weighted summaries |
| `loss_exposure` | Consequence term used in expected-loss calculation |

Action 0 represents no intervention and has zero direct intervention cost.

## `data/pipe_assets_public.csv`

| Column | Description |
|---|---|
| `asset_id` | Public synthetic pipe asset identifier assigned after shuffling |
| `length_m` | Pipe segment length in meters |
| `diameter_mm` | Pipe diameter in millimeters |
| `burial_depth_m` | Burial depth in meters |
| `age_years` | Relative service age used by the released model |
| `years_since_last_failure` | Relative years since last recorded failure event |
| `cost_minor_repair` | Cost of pipe action 1 |
| `cost_lining` | Cost of pipe action 2 |
| `cost_replacement` | Cost of pipe action 3 |
| `risk_weight` | Relative asset weight used for weighted summaries |
| `loss_exposure` | Consequence term used in expected-loss calculation |

Action 0 represents no intervention and has zero direct intervention cost.

## De-identification steps

The release applies the following transformations:

- Original road and pipe identifiers were removed.
- Rows were independently shuffled for each asset class.
- Public IDs were generated only after shuffling.
- Pipe absolute calendar years were converted to relative `age_years` and `years_since_last_failure`.
- Local filesystem paths and manuscript source locations were excluded.

