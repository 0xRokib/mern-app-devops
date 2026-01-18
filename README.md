# MERN Stack Task Manager

## 📖 Overview

This is a robust **Task Management Application** built using the **MERN** (MongoDB, Express.js, React, Node.js) stack. It demonstrates a complete full-stack workflow, including a modern frontend with **Vite** and **Tailwind CSS**, a scalable backend API, and containerization support using **Docker**.

This project is designed to showcase full-stack development skills, RESTful API design, and DevOps practices.

## 🚀 Features

- **Task Management**: Create, view, and delete tasks seamlessly.
- **Responsive Design**: Built with **Tailwind CSS** for a mobile-first, modern UI.
- **Real-time Updates**: Instant feedback on task creation and deletion.
- **Error Handling**: Graceful error management with user-friendly notifications.
- **Loading States**: Interactive Skeleton/Spinner loaders for better UX.
- **Dockerized**: Fully containerized application with `docker-compose` for easy deployment.

## 🛠️ Tech Stack

### Frontend

- **React.js**: (v19) Powered by **Vite** for fast development.
- **Tailwind CSS**: (v4) For rapid and customized styling.
- **JavaScript (ES6+)**: clean and modular code structure.

### Backend

- **Node.js & Express.js**: Robust REST API architecture.
- **MongoDB & Mongoose**: NoSQL database for flexible data storage.
- **Cors & Dotenv**: Middleware for security and configuration.

### DevOps

- **Docker**: Containerization for "write once, run anywhere".
- **Docker Compose**: Orchestration of multi-container environments (Client & Server).
- **GitHub Actions**: Automated CI/CD pipeline for linting, testing, and deployment.
- **AWS EC2**: Production hosting environment.

## ♾️ DevOps & CI/CD Pipeline

This project implements a fully automated **CI/CD pipeline** using **GitHub Actions**. Use this section to understand the automation workflow.

### 🔄 CI: Continuous Integration

Every push to `main` or `dev` branches triggers the `build-and-lint` job:

1.  **Linting**: Runs `eslint` for both Client and Server to ensure code quality.
2.  **Dependency Checks**: Verifies `npm ci` installs cleanly.
3.  **Docker Build**: Validates that both Frontend and Backend Docker images build successfully.

### 🚀 CD: Continuous Deployment

Upon a successful merge to the `main` branch, the `deploy` job automates the release:

1.  **SSH Connection**: Securely connects to the production **AWS EC2** instance.
2.  **Code Pull**: Fetches the latest code from the repository.
3.  **Orchestration**: Runs `docker-compose up -d --build` to safely restart services with zero configuration drift.
4.  **Cleanup**: Executes `docker image prune` to keep disk usage optimized.

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
