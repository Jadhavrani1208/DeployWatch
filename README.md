# DeployWatch 🚀

**Automated CI pipeline and Docker image publishing for a Spring Boot application.**

DeployWatch is a DevOps learning project built to practise continuous integration, automated testing, Docker containerization, and container image publishing using GitHub Actions and GitHub Container Registry (GHCR).

## ✨ Features

- **Spring Boot:** Java backend application.
- **Automated CI:** GitHub Actions workflow triggered by pushes and pull requests to `main`.
- **Automated Testing:** Maven build and test execution using `mvn -B clean verify`.
- **Docker:** Containerizes the Spring Boot application.
- **GitHub Container Registry:** Automatically publishes Docker images to GHCR after successful CI on pushes to `main`.
- **Health Monitoring:** Spring Boot Actuator health endpoint.

## 🛠️ Tech Stack

- Java 17
- Spring Boot
- Maven
- JUnit
- Docker
- GitHub Actions
- GitHub Container Registry (GHCR)
- Spring Boot Actuator

## ⚙️ CI/CD Workflow

1. Code is pushed to the `main` branch or a pull request targets `main`.
2. GitHub Actions checks out the source code.
3. Java 17 is configured.
4. Maven builds the application and runs tests.
5. Docker builds the application image.
6. On pushes to `main`, GitHub Actions authenticates to GHCR and publishes the image.

## 🐳 Run with Docker

Pull the published image:

```bash
docker pull ghcr.io/jadhavrani1208/deploywatch:latest
```

Run the container:

```bash
docker run -d --name deploywatch-app -p 8080:8080 ghcr.io/jadhavrani1208/deploywatch:latest
```

Check application health:

```text
http://localhost:8080/actuator/health
```

Expected response includes:

```json
{"groups":["liveness","readiness"],"status":"UP"}
```

If port `8080` is already in use, replace the host port with another available port, such as `8082`.

## 📦 Docker Image

`ghcr.io/jadhavrani1208/deploywatch:latest`

## 🎯 Learning Outcomes

- Building CI workflows with GitHub Actions.
- Automating Java builds and tests.
- Containerizing a Spring Boot application.
- Publishing container images to GHCR.
- Running and validating a containerized application.

## 🔮 Future Improvements

- Automated deployment to a hosting platform.
- Redis caching.
- Kafka-based event processing.
- Deployment history dashboard and monitoring.

## 👩‍💻 Author

**Rani Jadhav**

- GitHub: [Jadhavrani1208](https://github.com/Jadhavrani1208)
- Project repository: [DeployWatch](https://github.com/Jadhavrani1208/DeployWatch)

---

Built as a hands-on project to learn Java backend development and DevOps practices.
