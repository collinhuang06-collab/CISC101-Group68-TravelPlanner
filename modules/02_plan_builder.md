<!--
CHANGE LOG — Updated Nov 19, 2025
- Added explicit input requirements (dates, lodging, preferences, budget, transit modes)
- Added detailed activity schema (duration, cost, location, opening hours, weather dependency, tags)
- Clarified selection rules (time windows, proximity, pacing, theme diversification)
- Added feasibility checks (opening hours, travel time, reservations, budget alignment)
- Added backup option logic for weather, missing data, and unavailable activities
- Improved output formatting with time blocks, notes, costs, and backup options
-->


# Module 2 — Plan Builder (Options → Days)

Inputs
The plan builder requires the following explicit inputs:

Trip dates (start and end)

Lodging location (address or coordinates)

User preferences (interests, dietary needs, accessibility requirements, pacing style)

Budget (per-day and overall trip budget)

Transit modes (walking, public transport, rideshare, rental car, etc.)

Activity Schema
Each candidate activity must include:

Type (attraction, restaurant, park, event, etc.)

Estimated duration (minutes/hours)

Cost range (, $, $$$)

Location (coordinates or address)

Opening hours (daily schedule, closed days)

Ticketing/reservation requirements (yes/no, advance needed)

Accessibility notes (wheelchair access, dietary suitability, family-friendly)

Weather dependency (indoor/outdoor, seasonal suitability)

Tags (theme: culture, food, nature, shopping, nightlife, etc.)

Selection Rules
For each day, activities are chosen using the following rules:

Time windows:

Morning: 08:00–11:00

Midday: 11:30–14:00

Afternoon: 14:30–17:30

Evening: 18:00–21:00

Proximity rules:

Morning activity must be within 20–30 minutes of lodging.

Midday activity within 15–20 minutes of prior activity.

Afternoon activity allows longer transit (20–40 minutes).

Evening restaurant/activity near lodging or last activity.

Theme diversification: Avoid repeating the same primary tag (e.g., two museums in a row).

Pacing: Respect block durations, include 15–30 min transit buffers, and avoid overscheduling.

Feasibility Checks
Before confirming an activity:

Opening hours: Must overlap with the block’s time window.

Travel time: Transit duration must fit buffer constraints.

Reservations: Flag activities requiring advance booking; suggest alternatives if unavailable.

Budget alignment: Track cumulative daily cost; stay within ±10% of per-day budget.

Backup Options
For each block, maintain at least one fallback option:

Weather contingency: Indoor alternative for outdoor activities.

Missing data: Use category-based estimates for duration/cost if unavailable.

Unrealistic budgets: Suggest free/low-cost alternatives.

Unavailable activities: Provide “open slot” with 2–3 suggestions.

Output Formatting
Each day plan is presented with consistent blocks:

Day X

Morning: Activity name (type, duration, cost, distance, transit mode)

Notes: Opening hours, reservation flag, accessibility, weather dependency

Midday: Activity name (same schema)

Afternoon: Activity name (same schema)

Evening: Restaurant or optional event (same schema)

Summary:

Total estimated cost (per day)

Total transit time

Reservation requirements flagged

Backup options listed

Example (formatted output)
Day 1

Morning: Local café + waterfront walk (90 min, $, 10 min walk)

Notes: Indoor/outdoor mix, accessible, no reservation needed

Midday: City museum (120 min, $$, 15 min transit by bus)

Notes: Opens at 10:00, ticket required, indoor, accessible

Afternoon: Botanical gardens (90 min, $, 25 min transit by tram)

Notes: Outdoor, weather-dependent, backup: art gallery

Evening: Riverside restaurant (120 min, $$, 10 min walk)

Notes: Reservation recommended, accessible, indoor

Summary:

Total cost: $
–
$$

Transit time: ~60 min

Reservations: 1 required

Backup options: Art gallery (afternoon), casual diner (evening)
