# Tableside: IAM

The repo for Tableside's Identity and Access Management (IAM) deployment.

Uses [Keycloak](https://www.keycloak.org) behind an NGINX reverse proxy.

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
KC_HOSTNAME="auth.tableside.site"
KC_DB_URL_HOST="postgres"
KC_DB_URL_PORT="5432"
KC_DB_URL_DATABASE=${POSTGRES_DB}
KC_DB_USERNAME=${POSTGRES_USER}
KC_DB_PASSWORD=${POSTGRES_PASSWORD}

# - Let's Encrypt - #
LE_EMAIL="gg00528@surrey.ac.uk"
LE_OPTIONS="--staging --keep-until-expiring"
LE_RENEW_OPTIONS="--dry-run --no-self-upgrade --post-hook '"'nginx -s reload'"'"
LE_RENEW_CRON_COMMAND="echo 'Dummy cron command'"

```
5. Run `docker compose up`
6. Ensure all services start correctly.
7. Navigate to `localhost:8040`
