# Fluxzero Game Rental Sample

A standalone Java sample application demonstrating a game-rental domain with the Fluxzero SDK.

## What it demonstrates

- Command handling and event-sourced aggregates for registering, renting, and returning games.
- Document queries for catalog search and statistics.
- User management, roles, validation, and request authentication.
- HTTP endpoints and WebSocket updates.
- Side-effect handlers with retry and correction behavior.
- Fluxzero behavior tests and Spring integration tests.

## Quick start

Java 25 or newer is required. Run the tests with either wrapper:

```bash
./mvnw test
# or
./gradlew test
```

Start the complete local application stack:

```bash
./mvnw exec:java
# or
./gradlew runTestApp
```

This starts the Fluxzero test server, the Fluxzero proxy on `http://localhost:8080`, and the Spring Boot application.

## API endpoints

### User management

- **GET** `/api/users` - List all users.
- **POST** `/api/users` - Create a manager user.

### Game rental

- **GET** `/api/games` - Find games, optionally filtered by `term`.
- **POST** `/api/games` - Register a game.
- **GET** `/api/games/{id}` - Get game details.
- **POST** `/api/games/{id}/rent` - Rent a game.
- **POST** `/api/games/{id}/return` - Return a game.
- **GET** `/api/games/stats` - Get game statistics.

## Deployment

The manual `Deploy to Fluxzero Cloud` GitHub Actions workflow builds the Maven application and deploys its container.
Configure the repository's `FLUXZERO_API_KEY` secret before running it.

## License

Licensed under the Apache License 2.0. See [LICENSE](LICENSE).
