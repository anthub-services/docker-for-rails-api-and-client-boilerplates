# Docker for Rails API and Client Boilerplates

This project is based on the
[Node API and Client Boilerplate](https://github.com/anthub-services/node-api-and-client-boilerplate).
With [Docker](https://www.docker.com/), you can start all the services
([Node Express API Boilerplate](https://github.com/anthub-services/node-express-api-boilerplate),
[Create React App Boilerplate](https://github.com/anthub-services/create-react-app-boilerplate),
and Postgres database) with one bash command.

## Docker

Download and install the [Docker Community Edition](https://www.docker.com/community-edition).

## Bash Commands

Executable bash commands have been provided to easily execute Docker commands.
From the `root` directory of the project, run the following commands:

| Command                                | Description                                                    |
|----------------------------------------|----------------------------------------------------------------|
| `./bin/install`                        | Clone the apps, build the Docker containers, and initialise db |
| `./bin/reinstall`                      | Delete the apps and run the installation process               |
| `./bin/start`                          | Start all the services (API, client, and database)             |
| `./bin/stop`                           | Stop all the services                                          |
| `./bin/console <container ID or Name>` | Access the terminal console of the API or client containers    |

Note: To manage separate Docker instance for API or client,
open another terminal console and change the project directory from `root` to `api` or `client` and run the commands above.

### Database

| Command                         | Description                                               |
|---------------------------------|-----------------------------------------------------------|
| `./bin/pg/resetdb`              | Drop and re-initialise database                           |
| `./bin/pg/migrate`              | Run new schema migration                                  |
| `./bin/pg/migrateundo`          | Revert the recent schema migration                        |
| `./bin/pg/seed <seed file>`     | Run specific data seed file with or without .js extension |
| `./bin/pg/seedundo <seed file>` | Revert the seed of specific data seed file                |
| `./bin/pg/psql`                 | Access the database console                               |

Note: Used `./bin/pg/psql <database container ID or Name>` to access the database console.
To run the commands above for separate API Docker instance, simply change the project directory from `root` to `api`.

### CSS

| Command           | Description                                                         |
|-------------------|---------------------------------------------------------------------|
| `./bin/css/watch` | Watch and compile *.scss files on file changes (for Mac users only) |
| `./bin/css/build` | Manually compile *.scss files                                       |

Note: To run the commands above for separate client Docker instance, simply change the project directory from `root` to `client`.

## Install and Start the Apps
Run the `./bin/install` to clone the API and client apps and to initialise the database.
If the installation process is successful, both the API and client services shall be started.

## Users

Use the following credentials to test different API responses. Default password for all accounts is `password`.

- **Admin User:** `admin@email.com` - can access all applications
- **Admin User witout Settings page:** `admin_no_settings@email.com` - no access on admin Settings page
- **User redirected to internal page:** `referrer@email.com` – when `redirect.url` is set without the domain,
user shall be redirected to internal page if no location path (referrer) found on the Sign In page
- **User redirected to external page:** `redirect@email.com` – when `redirect.external` and `redirect.url` are set,
user shall be redirected to external page if no location path (referrer) found on the Sign In page
- **Blocked User:** `blocked@email.com` – user is signed in but the account is blocked
- **Unauthorized User:** simply enter wrong `email` and/or `password`
