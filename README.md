Funnela via docker compose
===

This example docker-compose file allows you to start Funnela in the minimal configuration.

Basic setup
---

When using this method it is recommended to make copy of an example `docker-compose.yml` file from this repository and modify security-related environment variables:

- `SUPERVISOR_PASSWORD` - Master password. Can be used to log in to any account. Lave empty to disable the feature
- `SECURITY_SALT` - String used in hashing password. Has to be exactly 32 alphanumeric characters.


When you're ready with your configuration, simply run:

```sh
docker compose up
```

Funnela is now running on port `80`. The default user is `admin` with password `admin`.


Restoring existing DB
---

Follow steps described in `Basic setup`. Next connect to the postgres server running in a container and replace the `funnela` db by restoring the backup. Restart whole docker compose stack. Database will be automatically updated to the most recent version which is compatible with docker - it might take some time. Use master password to login and change all the passwords.
