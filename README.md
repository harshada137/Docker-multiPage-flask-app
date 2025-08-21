# Docker-multiPage-flask-app
 This project demonstrates a multi-container application using Flask (Python) as the backend and Nginx as a reverse proxy. It serves dynamic HTML templates (home.html &amp; api.html) and is fully containerized with Docker Compose for easy setup and deployment.

# Multi-Container App (Flask + Nginx + Docker Compose)

This project demonstrates a multi-container setup using Python Flask (backend) and Nginx (reverse proxy) managed by Docker Compose.  
Both `/` and `/api` routes return HTML pages instead of plain text or JSON.


## 📂 Project Structure

multi-container-app/
├── docker-compose.yml
├── flask-app/
│   ├── Dockerfile
│   ├── app.py
│   ├── requirements.txt      # optional, can list flask here instead of Dockerfile
│   └── templates/
│       ├── home.html
│       └── api.html
└── nginx/
├── default.conf



## ⚙️ Services
 * Flask App → Serves HTML pages.  
  - `/` → Home Page (`home.html`)  
  - `/api` → API Page (`api.html`)  
 * Nginx → Reverse proxy.  
  - Forwards `/` and `/api` requests to the Flask app.  



## 🚀 Getting Started

1. Clone or Create Project   
* git clone <your-repo-url> multi-container-app
* cd multi-container-app


 2. Build & Run Containers
* docker compose up --build


3. Access Application
* Home Page: [http://localhost:8080/](http://localhost:8080/)
* API Page: [http://localhost:8080/api](http://localhost:8080/api)

4. Stop Containers
* docker compose down


✅ Notes
* Flask runs on port `5000` (inside container).
* Nginx listens on port `80` (mapped to host `8080`).
* Containers communicate internally over Docker’s default network.
