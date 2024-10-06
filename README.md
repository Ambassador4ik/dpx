# dpx

**dpx** is a powerful command-line tool designed to streamline the setup and management of local development environments. Acting as an abstraction layer over Docker Compose, dpx simplifies the orchestration of services by providing a rich library of pre-defined configurations for popular services like PostgreSQL, Kafka, Redis, and many more. This allows developers to quickly spin up and manage complex environments without directly dealing with Docker Compose files.

## 🚀 Key Features
- **Predefined Configurations:** Access a comprehensive library of ready-to-use configurations without directly interacting with Docker Compose files. 
- **Interactive Setup:** Easily configure service versions and environment variables through intuitive interactive prompts.
- **Quick Management:** Start, stop, restart, and delete services with simple commands.
- **Namespace Support:** Organize multiple projects and environments without conflicts.
- **Version Selection:** Choose from the most popular and stable versions of each service to ensure compatibility.
- **Log Monitoring:** View real-time logs for individual services to aid in debugging.
- **Environment Reset:** Erase service storage and reset environments effortlessly.

## 📦 Supported Services
- **Databases:** PostgreSQL, MySQL, MongoDB, Redis, Clickhouse
- **Message Brokers & Queues:** Apache Kafka, RabbitMQ
- **Web Servers & Proxy:** NGINX, Traefik
- **CI/CD Tools:** Jenkins, GitLab Runner
- **Other:** Prometheus, Grafana

## 🔧 Installation
**Prerequisites**
- **Docker**: Ensure Docker is installed and running on your machine.
- **Docker Compose**: Required for managing multi-container Docker applications.

Install via Homebrew (macOS)
```bash
brew tap ambassador4ik/dpx
brew install dpx
```

## 🛠 Quick Start
1. **Create a PostgreSQL server with default config:**
```bash
dpx run postgres
```
You will be provided with a link to your database:
```
PostgreSQL Configured! Running at:
postgresql://admin:randomPassword@localhost:5432
```

2. **Deploy a Kafka server on a specific namespace:**
```bash
dpx create kafka --name kafka-myservice --namespace myservice
```
If not specified, those arguments will be prompted interactively!

3. **Clean up your workspace:**
```bash
dpx stop --namespace myservice
dpx delete --namespace myservice
```
