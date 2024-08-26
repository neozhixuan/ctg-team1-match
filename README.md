# match

This repository contains two applications:

1. **food-match** - A modern full stack web application built with the T3 stack (TypeScript, Tailwind CSS, tRPC, and Next.js).
2. **ml-service** - A machine learning application built using Flask, which serves as an API endpoint for model predictions.

Both applications can be set up individually or together using Docker Compose.

## Table of Contents

- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
  - [1. T3 Full Stack App](#1-t3-full-stack-app)
  - [2. Flask ML App](#2-flask-ml-app)
- [Docker Compose Setup](#docker-compose-setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Structure

```
├── food-match/
│   ├── src/
│   ├── public/
│   ├── prisma/
│   ├── package.json
│   ├── Dockerfile
│   └── ...
├── ml-service/
│   ├── test.py
│   ├── requirements.txt
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

## Prerequisites

Before setting up the applications, ensure you have the following installed:

- [Node.js 18.20.3](https://nodejs.org/) (for food-match - version maintained by .nvmrc)
- [pnpm](https://pnpm.io/installation) (package manager)
- [Python 3.10.12](https://www.python.org/) (for ml-service)
- [Docker](https://www.docker.com/) and [Docker Compose](https://docs.docker.com/compose/) (optional, for Docker setup)

## Setup Instructions

### 1. food-match

#### Step 1: Install Dependencies

Navigate to the `food-match` directory and install the required Node.js packages:

```bash
cd food-match
pnpm install
pnpm build
```

#### Step 2: Configure Environment Variables

Create a `.env` file in the `food-match` directory and add your environment variables. Use the `.env.sample` file as a reference.

#### Step 3: Run the Application

Start the development server:

```bash
pnpm dev
```

The app should now be running at `http://localhost:3000`.

### 2. Flask ML App

#### Step 1: Create a Virtual Environment

Navigate to the `Flask-ML-app` directory and create a virtual environment:

```bash
cd ml-service
python -m venv venv
source venv/bin/activate  # On Windows use \`venv\Scripts\activate\`
```

#### Step 2: Install Dependencies

Install the required Python packages:

```bash
pip install -r requirements.txt
```

#### Step 3: Run the Application

Run the Flask development server:

```bash
python test.py
```

The Flask ML App should now be running at `http://localhost:5000`.

## Docker Compose Setup

To set up both applications using Docker Compose, follow these steps:

### Step 1: Build and Start Services

In the root directory of the repository, run:

```bash
docker-compose up --build
```

This command builds and starts both the T3 Full Stack App and the Flask ML App using Docker containers.

### Step 2: Access the Applications

- **food-match**: `http://localhost:3000`
- **ml-service**: `http://localhost:5000`

## Usage

- **food-match**: The frontend and backend of our application, serving routes and interfaces, with secure type enforcement and form validation using Zod.
- **ml-service**: This is a Flask app that runs a cosine similarity search and vectoriser endpoint.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
