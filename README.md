# Budget Bees Database

This project manages the database schema migrations for the Budget Bees application using Liquibase.

## Structure

- `src/main/resources/db/changelog/db.changelog-master.yaml`: The master Changelog file that aggregates all changes.
- `src/main/resources/db/changelog/changes`: Directory containing individual YAML migration files.

## Prerequisites

- **Java 21** or higher
- **Maven** (A Maven Wrapper `mvnw` is included)

## Usage

### Running Migrations Manually

To run migrations against a specific database, you can use the Maven Liquibase plugin. configuration is typically passed via command line arguments or a properties file.

```bash
./mvnw liquibase:update \
  -Dliquibase.url=jdbc:postgresql://localhost:5432/budget_bees \
  -Dliquibase.username=your_username \
  -Dliquibase.password=your_password
```

### Integration with API

The `budget-bees-api` project references this directory to run migrations automatically during integration tests using Testcontainers.

## Creating a New Migration

1. Create a new YAML file in `src/main/resources/db/changelog/changes/` (e.g., `003-create-new-table.yaml`).
2. Define your changeset.
3. Include the new file in `src/main/resources/db/changelog/db.changelog-master.yaml`.

Example Changeset:

```yaml
databaseChangeLog:
  - changeSet:
      id: 3
      author: your-name
      changes:
        - createTable:
            tableName: example_table
            columns:
              - column:
                  name: id
                  type: bigint
                  autoIncrement: true
                  constraints:
                    primaryKey: true
```
