# Copilot Instructions for the Acquisitions Project

Welcome to the Acquisitions codebase! This document provides essential guidelines for AI coding agents to be productive in this project. It outlines the architecture, workflows, conventions, and integration points specific to this repository.

## Project Overview

The Acquisitions project is a Node.js-based application with the following key components:

- **`src/`**: Contains the main application logic, organized into subdirectories for controllers, services, models, routes, middleware, and utilities.
- **`drizzle/`**: Includes database migration files and metadata.
- **`logs/`**: Stores application logs.
- **Configuration Files**: Key configurations are located in `drizzle.config.js`, `eslint.config.js`, and `src/config/`.

### Major Components

1. **Controllers** (`src/controllers/`): Handle HTTP requests and responses. Example: `auth.controller.js` manages authentication-related endpoints.
2. **Services** (`src/services/`): Contain business logic. Example: `auth.service.js` handles authentication logic.
3. **Models** (`src/models/`): Define data structures and interact with the database. Example: `user.model.js` represents user data.
4. **Routes** (`src/routes/`): Define API endpoints and map them to controllers. Example: `auth.routes.js` sets up authentication routes.
5. **Utilities** (`src/utils/`): Provide helper functions. Example: `jwt.js` manages JSON Web Token operations.
6. **Validations** (`src/validations/`): Define input validation schemas. Example: `auth.validation.js` validates authentication-related inputs.

### Data Flow

1. **Request Handling**: Routes map incoming requests to controllers.
2. **Business Logic**: Controllers delegate tasks to services.
3. **Database Interaction**: Services interact with models to query or update the database.
4. **Response**: Processed data is sent back to the client via controllers.

## Developer Workflows

### Installation

Run the following command to install dependencies:

```bash
npm install
```

### Running the Application

Start the application with:

```bash
npm start
```

### Testing

Tests are not explicitly defined in the current structure. Add tests under a `tests/` directory and use a testing framework like Jest or Mocha.

### Debugging

Use the `logs/` directory to review application logs. The `logger.js` file in `src/config/` configures logging behavior.

### Database Migrations

Database migrations are managed using Drizzle. Migration files are located in `drizzle/`.

## Project-Specific Conventions

1. **Error Handling**: Use centralized error handling middleware.
2. **Validation**: Define validation schemas in `src/validations/` and apply them in controllers.
3. **Logging**: Use the logger configured in `src/config/logger.js`.
4. **Environment Variables**: Store sensitive data in environment variables and access them via `process.env`.

## Integration Points

- **Database**: Managed via Drizzle ORM. Configuration is in `src/config/database.js`.
- **Authentication**: JSON Web Tokens (JWT) are used for authentication. Relevant files: `src/utils/jwt.js`, `src/services/auth.service.js`.
- **Logging**: Logs are written to `logs/combined.log` and `logs/error.log`.

## Examples

### Adding a New Route

1. Create a new route file in `src/routes/`.
2. Define the route and map it to a controller function.
3. Update `src/index.js` to include the new route.

### Adding a New Service

1. Create a new service file in `src/services/`.
2. Implement the business logic.
3. Update the relevant controller to use the new service.

---

This document is a living guide. Update it as the project evolves to ensure it remains accurate and helpful.
