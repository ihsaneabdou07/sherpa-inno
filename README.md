# decarb-dss

Decision-support prototype for a decarbonised energy ecosystem in Morocco
(PV, wind, storage, desalination, electrolysis, synthetic fuels).

## Setup
    python -m venv .venv
    source .venv/bin/activate        # Windows: .venv\Scripts\activate
    pip install -r requirements.txt
    pytest -q

## Conventions
- Time: UTC, typical year of 8760 hours (no 29 February)
- Units: power kW, energy kWh, mass kg, water m3
- Code, variable names and comments in English
- All parameters live in config/*.yaml, never hard-coded
- Weather CSV columns: timestamp_utc, ghi_wm2, t2m_c, ws100_ms

## Module interface
Every module in models/ exposes
    simulate(inputs: pd.DataFrame, params: dict) -> pd.DataFrame
with hourly rows (8760) and units kW / kWh / kg.

## Git workflow
One branch per member (m1/..., m2/...), pull request, one review, squash merge.
