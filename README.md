# Masarat

A workflow and task management system with the visual identity of the Ministry of Public Works and Housing, supporting Syrian Arabic, English, and right-to-left layouts.

## Features

- Create reusable workflow templates with defined steps and assignees.
- Run multiple workflows, assign tasks, and track progress and deadlines.
- Manage teams, groups, and permissions.
- Share forms, attach files, leave comments, and receive notifications.
- View reports and integrate with other systems through the API.

## Requirements

- Git and Docker with Docker Compose v2. On Windows, use Docker Desktop with Linux containers.
- At least 8 GB of RAM (16 GB recommended) and 50 GB of disk space.
- Available local ports `80`, `443`, `8001`, and `15672` for the Docker Compose services.

## Installation

1. Clone the repository and enter its directory:

   ```shell
   git clone https://github.com/samirajaj/pneumaticworkflow.git
   cd pneumaticworkflow
   ```

2. Copy `default.env` to `.env` in the project root. If `.env` already exists, edit it directly. Set Syrian Arabic as the default language:

   ```dotenv
   LANGUAGE_CODE=ar-sy
   ```

   Use `en` for English. See [default.env](default.env) for server, database, and email settings. Set passwords and `DJANGO_SECRET_KEY` before deploying to a shared or public server.

3. Build and start the services from local source:

   ```shell
   docker compose up -d --build
   ```

   The first startup may take several minutes. Once ready, open [http://localhost](http://localhost) and create an account. The admin panel is available at [http://localhost:8001/admin](http://localhost:8001/admin).

To access the application from another device, set `SERVER_ADDRESS`, `FRONTEND_URL`, `BACKEND_URL`, `FORMS_URL`, and `WSS_URL` in `.env` to match your server address. For a public deployment, configure HTTPS and email for your environment.

## Useful Commands

```shell
docker compose ps          # Check service status
docker compose logs -f     # Follow logs
docker compose down        # Stop services
```

## Further Documentation

- [Syrian Arabic and RTL support](RTL_IMPLEMENTATION_STATUS.md)
- [Masarat visual identity](BRANDING_IMPLEMENTATION.md)

## Attribution and License

Based on [Pneumatic](https://github.com/pneumaticapp/pneumaticworkflow) by Pneumatic Software, Inc. Licensed under [Apache 2.0](LICENSE).
