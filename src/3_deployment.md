# Deployment

Deployment process will vary depending on the environment you are deploying to, but this guide will help you with a basic docker-compose deployment.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [PostgreSQL](https://www.postgresql.org/download/)
- SMTP server for sending emails
- A registered Telegram Bot

## Instructions

1. Clone the repository

```bash
git clone https://github.com/TheSharpOwl/inno-alumni-portal.git
cd inno-alumni-portal
```

2. Create a `.env` file in the root of the project with the following content, substituting values in `<...>` with your own values:

```env
DATABASE_HOST=<PostgreSQL database address>
DATABASE_PORT=<PostgreSQL database port>
DATABASE_PASSWORD=<PostgreSQL database password>
DATABASE_NAME=<PostgreSQL database name, for example inno_alumni_portal>
DATABASE_USERNAME=<PostgreSQL database username, for example postgres>
ALGORITHM=<algorithm to use for JWT, for example HS256>
SECRET_KEY=<secret key for JWT, make sure to use a long random string>
ACCESS_TOKEN_EXPIRE_MINUTES=<access token expiration time in minutes, for example 30>
MAIL_FROM=<email address to send emails from>
MAIL_FROM_NAME=<email name to send emails from>
MAIL_USERNAME=<mail account to log into>
MAIL_PASSWORD=<mail account password>
MAIL_SERVER=<mail server address>
MAIL_PORT=<mail server port>
```

3. Create venv and install python dependencies:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

3. Replace the telegram bot token in `app/telegram/data.py` with your own token.

4. Initialize the database with `prisma`:

```bash
prisma generate
prisma db push
```

5. Run the application with `docker-compose`:

```bash
docker-compose up
```

You can also use `docker-compose-prod.yml` if you want let's encrypt certificates and a reverse proxy with `nginx`, but maybe you have another way to do that.