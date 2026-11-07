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

## Running locally
Build the graph (only when data changes):
```
MSYS_NO_PATHCONV=1 docker run --rm -e JAVA_TOOL_OPTIONS=-Xmx8g -v "$(pwd -W)/otp:/var/opentripplanner" opentripplanner/opentripplanner:latest --build --save
```

Start OTP, then open http://localhost:8080:
```
MSYS_NO_PATHCONV=1 docker run -it --rm -p 8080:8080 -e JAVA_TOOL_OPTIONS=-Xmx8g -v "$(pwd -W)/otp:/var/opentripplanner" opentripplanner/opentripplanner:latest --load --serve
```