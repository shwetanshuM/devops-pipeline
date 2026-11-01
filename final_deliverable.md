# DevOps Assignment: CI/CD Pipeline for a Python Service

## Service
A small Flask app with two endpoints:
- `/` returns a hello message
- `/health` returns `{"status": "ok"}`

## Pipeline (GitHub Actions)
Defined in `.github/workflows/ci-cd.yml`. On every push or pull request to `main`:
1. Check out the code
2. Set up Python 3.12 and install dependencies
3. Run pytest
4. Build the Docker image
5. Run the image as a container (`docker run -d -p 8000:8000`)
6. Smoke test: curl `/health` with retries
7. Clean up the container

## Run locally
    docker build -t devops-assignment .
    docker run -d -p 8000:8000 devops-assignment
    curl localhost:8000/health

## Successful run
<paste the link to your Actions run here>