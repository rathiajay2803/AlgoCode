# Code Compilation & Execution Platform

## Overview

This repository contains the source code for a highly scalable, microservices-based platform designed for online code compilation and execution. The platform supports multiple programming languages, provides real-time feedback to users, and ensures seamless scalability with AWS deployment.

## Features

- **Scalable Microservices Architecture:** Designed for high availability and seamless scalability using AWS auto-scaling and load balancing.
- **Multi-Language Code Execution:** Supports Java, Python, and C++ using Dockerized execution environments.
- **Efficient Problem Management:** A dedicated Problem Admin Service for CRUD operations on problems, including complex test cases and code stubs.
- **Optimized Execution Strategy:** Implements Strategy and Factory design patterns to optimize execution environments and manage Time Limit Exceeded (TLE) conditions.
- **High-Performance Submission Service:** Utilizes Fastify for handling a high volume of requests with exceptional performance.
- **Asynchronous Communication:** Uses Redis message queues for seamless integration between submission and executor services.
- **Real-Time Feedback:** WebSocket services provide immediate updates to users.
- **Robust AWS Deployment:** Deployed with auto-scaling groups, load balancers, and monitoring tools for optimal performance and fault tolerance.

## Repository Structure

This repository contains three microservices, each in its own folder with its own `.git` file for better organization and clarity.

```
root-directory/
│-- AlgoCode-Evaluator-Service/    # Microservice for problem management
│-- CodeChallengerBackend/         # Microservice for code execution
│-- SubmissionService/       # Microservice for handling user submissions
```

## Microservices Overview

### 1. Problem Admin Service

- **Path:** `problem-admin-service/`
- Built with JavaScript, Express, and MongoDB.
- Manages problem creation, updates, deletions, and test cases.

### 2. Executor Service

- **Path:** `executor-service/`
- Developed using TypeScript and Express.
- Runs Dockerized execution environments for multiple programming languages.
- Handles timeouts and optimizes execution strategy.

### 3. Submission Service

- **Path:** `submission-service/`
- Implemented using Fastify.
- Handles high-volume request processing.
- Uses Redis for message queuing and WebSockets for real-time feedback.

## Technologies Used

- **Backend:** JavaScript, TypeScript, Express, Fastify
- **Database:** MongoDB
- **Message Queue:** Redis
- **Containerization:** Docker
- **Cloud Services:** AWS (Auto Scaling, Load Balancers, Monitoring)
- **Real-Time Communication:** WebSockets

## Setup & Installation

1. Clone the repository:
   ```bash
   git clone --recurse-submodules https://github.com/your-repo-name.git
   cd your-repo-name
   ```
2. Navigate to each microservice and install dependencies:
   ```bash
   cd AlgoCode-Evaluator-Service && npm install
   cd ../CodeChallengerBackend && npm install
   ```
3. Set up environment variables:
   - Create a `.env` file inside each microservice folder and configure necessary variables.
4. Start services:
   ```bash
   docker-compose up --build
   ```

## Contribution

Feel free to fork this repository, create feature branches, and submit pull requests!
