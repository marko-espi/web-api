# Web API

A high-performance, lightweight RESTful API built in Go (Golang) for managing a movie database. This project is structured for scalability, featuring clean routing, structured middleware, and robust API handlers.

## 🚀 Features

- **Fast & Lightweight:** Built leveraging Go's native performance and concurrency primitives.
- **RESTful Architecture:** Clear separation of concerns between routing, business logic, and data handling.
- **Structured Middleware:** Integrated panic recovery and custom error responses.
- **Advanced Querying:** Supports full-text search, filtering by genres, pagination, and dynamic sorting.
- **Optimistic Concurrency:** Uses versioning to handle concurrent updates safely.
- **Structured Logging:** Implements Go's `slog` for JSON-formatted logging.

## 🛠️ Tech Stack

- **Language:** Go 1.21+
- **Routing:** [httprouter](https://github.com/julienschmidt/httprouter)
- **Database:** PostgreSQL
- **Database Driver:** [lib/pq](https://github.com/lib/pq)

## 📋 Prerequisites

- **Go:** Version 1.21 or higher.
- **PostgreSQL:** A running instance with a database created.
- **Environment Variable:** Set `GREENLIGHT_DB_DSN` to your PostgreSQL connection string (e.g., `postgres://user:pass@localhost/dbname?sslmode=disable`).

## ⚙️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/marko-espi/web-api.git
   cd web-api
   ```

2. **Download dependencies:**
   ```bash
   go mod download
   ```

3. **Run database migrations:**
   (Ensure you have a migration tool installed to apply files in the `migrations/` directory).

4. **Start the application:**
   ```bash
   go run ./cmd/api -db-dsn=$GREENLIGHT_DB_DSN
   ```

## 🛤️ API Endpoints

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| GET | `/v1/healthcheck` | Check API status |
| GET | `/v1/movies` | List movies (supports filtering & pagination) |
| POST | `/v1/movies` | Create a new movie |
| GET | `/v1/movies/:id` | Show details of a specific movie |
| PATCH | `/v1/movies/:id` | Partially update a movie |
| DELETE | `/v1/movies/:id` | Delete a movie |

## 🛠️ Development

- **Build:** `go build -o ./bin/api ./cmd/api`
- **Test:** `go test ./...`
