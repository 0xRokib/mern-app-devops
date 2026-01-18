# MERN Stack Task Manager

## 📖 Overview

This is a robust **Task Management Application** built using the **MERN** (MongoDB, Express.js, React, Node.js) stack. It demonstrates a complete full-stack workflow, including a modern frontend with **Vite** and **Tailwind CSS**, a scalable backend API, and containerization support using **Docker**.

This project is designed to showcase full-stack development skills, RESTful API design, and DevOps practices.

## 🚀 Features

## 🚀 Projects Highlights

### 🔧 DevOps & Infrastructure

- **Automated CI/CD**: Complete GitHub Actions pipeline for linting, testing, and deployment.
- **Container Orchestration**: Multi-container setup using **Docker Compose** for consistency.
- **Cloud Native**: Hosted on **AWS EC2** with secure SSH-based automatic deployments.
- **Infrastructure Maintenance**: Automated cleanup and resource optimization scripts.

### 💻 Application Features

- **Task Management**: Create, read, and delete operations with optimisic UI updates.
- **Responsive UI**: System-font stack with **Tailwind CSS** for superior performance.
- **Error Handling**: Graceful degradation and user-friendly error boundaries.

## ♾️ DevOps & CI/CD Pipeline

This project demonstrates a production-grade **DevOps workflow**, automating the path from code commit to cloud deployment.

### 🔄 CI: Continuous Integration Protocol

Triggered on updates to `main`, this stage ensures code integrity:

1.  **Static Code Analysis**: Runs `eslint` across the monorepo to enforce code quality standards.
2.  **Dependency Integrity**: Uses `npm ci` for deterministic dependency resolution.
3.  **Build Validation**: Compiles Docker images for both services to verify deployability.

### 🚀 CD: Continuous Deployment Strategy

Automated delivery to **AWS EC2** infrastructure:

1.  **Secure Handshake**: Establishes SSH connection using encrypted GitHub Secrets.
2.  **Artifact Retrieval**: Fetches the latest commits directly on the production host.
3.  **Container Relaunch**: Executes `docker-compose up -d --build` for seamless service updates.
4.  **Resource Optimization**: Runs `docker image prune -f` to prevent storage bloat.

## 📂 Project Structure

```bash
mern-devOps/
├── client/                 # React Frontend
│   ├── src/                # Source code (Components, Services, etc.)
│   ├── public/             # Static assets
│   ├── Dockerfile          # Frontend container config
│   └── ...
├── server/                 # Express Backend
│   ├── models/             # Mongoose Models
│   ├── routes/             # API Routes
│   ├── controllers/        # Business Logic
│   ├── Dockerfile          # Backend container config
│   └── ...
└── docker-compose.yml      # Orchestration config
```

## 🏁 Getting Started

### Prerequisites

- **Node.js** (v16+)
- **npm** or **yarn**
- **Docker** (optional, for containerized run)
- **MongoDB** (local or Atlas URI)

### Option 1: Run Locally

1.  **Clone the Repository**

    ```bash
    git clone https://github.com/your-username/mern-devOps.git
    cd mern-devOps
    ```

2.  **Setup Backend**

    ```bash
    cd server
    npm install
    # Create a .env file
    echo "PORT=5001" >> .env
    echo "MONGODB_URI=your_mongodb_connection_string" >> .env
    npm run dev
    ```

3.  **Setup Frontend**

    ```bash
    # Open a new terminal
    cd client
    npm install
    npm run dev
    ```

    The app will be available at `http://localhost:5173`.

### Option 2: Run with Docker 🐳

1.  Make sure Docker Desktop is running.
2.  Run the following command in the root directory:
    ```bash
    docker-compose up --build
    ```
    This will spin up the Client and Server containers. The application connects to a MongoDB Atlas cluster (configured in `.env`).

## 📡 API Endpoints

| Method   | Endpoint         | Description            |
| :------- | :--------------- | :--------------------- |
| `GET`    | `/api/tasks`     | Fetch all tasks        |
| `POST`   | `/api/tasks`     | Create a new task      |
| `DELETE` | `/api/tasks/:id` | Delete a specific task |

## 🔮 Future Enhancements

- [ ] Edit Task functionality.
- [ ] User Authentication (JWT).
- [ ] Drag and drop task reordering.
- [ ] Dark Mode toggle.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
