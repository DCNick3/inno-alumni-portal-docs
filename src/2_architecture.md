# Architecture

The project consists of two services: the frontend and the backend.

The frontend is a Next.js application and is located in the `src` directory.

The backend is a Python FastAPI application and is located in the `app` directory. It uses Prisma as an ORM and PostgreSQL as a database.

The backend service also handles the Telegram bot, which can be used to access the services with a chat interface. It is located in the `app/telegram` directory. 