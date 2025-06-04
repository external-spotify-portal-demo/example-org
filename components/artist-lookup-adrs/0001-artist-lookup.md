# ADR 001: Decision to the Artist Lookup Service

## Status
Accepted

## Context
We need a lightweight and demonstrative application that showcases how a user can search for and retrieve information about musical artists. This service will be used primarily for demos, tutorials, and internal testing.

The primary use cases include:
- Searching for artists by name.
- Retrieving metadata such as genre, biography, and top tracks.
- Providing a simple and intuitive API for integration with front-end clients or other services.

Several options were considered:
1. Use a static dataset with no external dependencies.
2. Integrate with a third-party music API (e.g., MusicBrainz, Spotify).
3. Build a custom backend and database to manage artist data.

## Decision
We decided to build a demo artist lookup service using a third-party music API. This provides a balance between rich data availability and development simplicity. We will use MusicBrainz as the primary data source because it is free, has an open license, and provides comprehensive artist information.

## Consequences
- Rapid development is possible due to the use of existing APIs.
- The service will require internet access to retrieve data from MusicBrainz.
- We avoid the overhead of maintaining our own artist database.
- Dependency on the uptime and availability of the MusicBrainz API.

## Alternatives Considered
- **Static Dataset**: Not flexible or realistic for a demo environment.
- **Custom Backend**: Too heavy for the demo scope and would require ongoing maintenance.

## Related Decisions
- ADR 002: API Design for the Lookup Service
- ADR 003: Front-End Integration Plan
