# Contribution

If you wish to contribute to this project, you would need to setup a development environment. The following steps will guide you through the process.

## Guidelines

We don't have concrete contribution guidelines established, just be reasonable and respectful. Before working on a feature, please discuss it with the maintainers in an issue. We are open to any suggestions and improvements.


## Instructions

First of all, set up the `.env` file, the python virtual environment and the database as described in the [deployment guide](./3_deployment).

Then you would need to start frontend and backend development servers.

### Frontend

1. Install dependencies:

```bash
npm install
```

2. Start the development server:

```bash
npm start
```

### Backend

After making sure you are in the python virtual environment, run the following command:

```bash
uvicorn app.main:app --reload
```

### Making and submitting changes

Fork the repository, create a new branch and make changes. After you are done, submit a pull request to the main repository. We will make sure to review it as soon as possible.
