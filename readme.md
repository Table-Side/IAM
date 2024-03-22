# Tableside: IAM Deployment

The repo for Tableside's Identity and Access Management (IAM).

Uses [Keycloak](https://www.keycloak.org)

## Local Setup

1. Clone this repo
2. Ensure Docker is installed
3. Create a `.env` file:
```env
# - Postgres - #
POSTGRES_DB="keycloak"
POSTGRES_USER="keycloak"
POSTGRES_PASSWORD="passw0rd"

# - Keycloak - #
KEYCLOAK_ADMIN="admin"
KEYCLOAK_ADMIN_PASSWORD="passw0rd"
KC_DB="postgres"
KC_DB_URL="jdbc:postgresql://postgres:5432/keycloak"
KC_DB_USERNAME="keycloak"
KC_DB_PASSWORD="passw0rd"
```
5. Run `docker compose up`
6. Ensure all services start correctly.
7. Navigate to `localhost:8040`
