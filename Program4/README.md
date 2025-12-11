# Simple Flask Web Application with Docker

## Steps to Run the Project

### 1. Create the project files
- `app.py` (Flask application)
- `requirements.txt` (Python dependencies)
- `Dockerfile` (To containerize the app)

### 2. Install dependencies (optional for local testing)
```
pip install -r requirements.txt
```
### 3. Build the Docker image
```
docker build -t student-portal:v1 .
```

### 4. Run the Docker container with port mapping
```
docker run -d --name student-portal -p 5000:5000 student-portal:v1
```

### 5. Open in a browser
```
http://localhost:5000
```

You should see **Student Portal — Simple Flask App** running inside a Docker container.

---
