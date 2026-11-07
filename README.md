# relay-transit
Multimodal NYC trip planner (walk + Citi Bike + subway)

## MVP
Given two NYC addresses, show the 3 best routes mixing walking,
Citi Bike, and subway, with total time and estimated cost.

## Architecture
browser (React) → backend (FastAPI) → OpenTripPlanner 2

## Data sources
- OpenStreetMap (streets, bike lanes)
- MTA GTFS (subway schedules)
- Citi Bike GBFS (live bike/dock availability)