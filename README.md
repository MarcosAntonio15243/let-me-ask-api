# Let Me Ask API

An API developed during **NLW Agents** by **Rocketseat** for live streams and broadcasts, which uses an AI agent to predict answers to questions in real time.

> 🧪 This is the first version of the project, exactly as taught during the event. I intend to implement improvements in the future or use it as a base for similar projects.

## 📑 Table of Contents

- [Technologies](#technologies)
- [Setup and Configuration](#setup-and-configuration)
- [Running the Project](#running-the-project)
- [API Endpoints](#api-endpoints)
- [Author](#author)

## Technologies

The project was developed using the following stack:

- **Node.js** + native **TypeScript** (experimental strip types) — modern and typed development
- **Fastify** — lightweight, fast, and efficient web framework
- **PostgreSQL** + **pgvector** — data persistence with support for vectors and vector search
- **Drizzle ORM** — type-safe operations on the database
- **Zod** — robust schema and data validation
- **Docker** — database containerization for easy setup and deployment
- **Biome** — code linting and formatting to maintain quality and consistency

## Setup and Configuration

Below is a step-by-step guide for running this project.

### 1. Prerequisites

To run this project, make sure you have the following installed and configured on your system:

- [Node.js](https://nodejs.org) (use a version that supports `--experimental-strip-types`)
- [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose)

### 2. Clone this Repository

Example using SSH:

```bash
git clone git@github.com:MarcosAntonio15243/let-me-ask-api.git
```

### 3. Install Dependencies

For this project and documentation tutorial, we will use the [NPM](https://www.npmjs.com) package manager. To install the dependencies, run the following command at the root of the cloned repository:

```bash
npm install
```

### 4. Docker and Database

To set up the **PostgreSQL** database with the **pgvector** extension, run the following command at the root of the repository:

```bash
docker-compose up -d
``` 

> 💡 **Note**: Make sure no application is using port 5432, as it is the default database port for this project.
> - If the port is already in use, you can temporarily stop the service using it, or
> - Change the port in the docker-compose.yaml file to one that is available on your machine.

### 5. Configure Environment Variables

Create a `.env` file at the root of the project with the following format:

```env
# HTTP API port
PORT=

# Database URL
DATABASE_URL=

# Gemini API key
GEMINI_API_KEY=
```

### 6. Run Database Migrations

To run the database migrations, execute:

```bash
npx drizzle-kit migrate
```

### 7. (Optional) Seed the Database

If you want to seed the database with initial data, run:

```bash
npm run db:seed
```

## Running the Project

Once all setup steps are completed, run the following command to start the project:

- For **development** environment:
  
  ```bash
  npm run dev
  ```

- For **production** environment:

  ```bash
  npm start
  ```

## API Endpoints

You can explore and test the available API endpoints using the documentation below.

The default base url is: `http://localhost:3333`.

- `GET /health` - Verifies if the API is running properly.
- `GET /rooms` - Retrieves a list of all available rooms.
- `POST /rooms` - Creates a new room.
- `GET /rooms/{roomId}/questions` - Retrieves all questions from a specific room.
- `POST /rooms/{roomId}/questions` - Submits a new question to a specific room.

## Author

Made with  [Marcos Antonio](https://github.com/MarcosAntonio15243).

- 💻 Full Stack developer dedicated to building complete solutions by combining modern, functional user interfaces with robust back-end architectures.
- 📚 This project represents my first experience using tools like **Drizzle ORM** and the **pgvector** extension, with a focus on AI-powered APIs based on multimedia content.
- 🚀 Always open to feedback, collaboration, or ideas for improvement!
- 📫 Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/marcos-antonio-18059b234) or check out more of my projects here on GitHub.