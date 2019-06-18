# scooter-tracker
You have a fleet of 50 scooters in San Francisco. Your goal is to construct REST API endpoints and responses for these clients.

Since Spin relies on geographical features of PostgresQL, your challenge will be to implement a few geo-related features from our backend. Of course, your are not expected to build a frontend for these, but instead use your tests as the interface.

## Setup and requirements
Create a Github repository and invite jsierles to it. We'll fork this repo into our org so we can review.

Push code regularly with meaningful commit messages.

Setup a PostgreSQL instance with the PostGIS extension for testing locally.

Do not add an authentication layer to this service.

Tests are required, though not at 100% coverage.

Test enough to make you confident that the feature will work. Use your best judgement here. If you think of edge cases, include them as you see fit!

You must use PostGIS functions somewhere in your code. Don't rely only on Ruby gems to perform geographic calculations.

## Challenge details
You have a fleet of 50 scooters in San Francisco. Your goal is to construct REST API endpoints and responses for these clients.

### A scooter reporting its current location and battery life
Vehicles will report their lat/long and battery level, every 5 seconds, during a trip.

### A mobile app used by our operations team
This app should be able to:
- Open a maintenance ticket
- Mark a scooter as inactive and being picked up for maintenance
- Request that a batch of scooters be unlocked all at once

### A mobile app used by customers
This app should be able to show where active scooters are on a map within a given radius from the user's current lat/long location.

- Active scooters are defined as those having >= 30% battery life and not picked up for maintenance.
- <b>Bonus points:</b> Scooters should only be visible during the 9am - 5pm riding window in the US Pacific time zone.
- City governments requesting a historical data feed
  - This feed should confirm to a JSON schema spec.
  - The feed should any state transition through which the scooter has run, such as:

   - battery life being updated
   - location being updated
   - maintenance state changes

## Things we'll ask you about in code review
- How would you design this data model to efficiently handle historical data queries when that table reaches 100M records?
- Where are there be caching opportunities?
