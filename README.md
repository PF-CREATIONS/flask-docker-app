## Dockerfile

```dockerfile
FROM python:3.12
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python3", "app.py"]
```

| Instruction | Purpose |
|---|---|
| `FROM` | Uses the official Python 3.12 image as the base |
| `WORKDIR` | Sets `/app` as the working directory inside the container |
| `COPY` | Copies project files into the image |
| `RUN` | Installs dependencies from `requirements.txt` |
| `EXPOSE` | Documents that the app listens on port 5000 |
| `CMD` | Runs the app when the container starts |

## Getting Started

### Build the image
```bash
docker build -t flask-app:v1 .
```

### Run the container
```bash
docker run -p 5000:5000 flask-app:v1
```

### Access the app
Visit `http://localhost:5000` in your browser.

## What I Learned
- Docker images vs. containers
- Writing and structuring a Dockerfile
- Layer caching and why instruction order affects build speed
- Port mapping between host and container
- Build context and base images

## Key Takeaway
Docker reuses cached layers when rebuilding an image if the underlying files haven't changed — this speeds up builds significantly, and it's why the order of instructions in a Dockerfile matters (less frequently changed steps first).

## Next Steps
This project is the first milestone in an ongoing DevOps learning journey. Topics coming up next:
- Docker Volumes & Networks
- Docker Compose
- Pushing/pulling images to Docker Hub
- Multi-stage builds
- Kubernetes basics
- CI/CD pipelines

## Author
**Malik Muhammad Ahad**
Computer Systems Engineering student | Learning DevOps by building real projects
[GitHub](https://github.com/PF-CREATIONS) · [LinkedIn](https://linkedin.com/in/malik-muhammad-ahad/)
