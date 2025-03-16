# cydra-docker
CyDRA AI containerised version

How to Run the Containerized CyDRA Application

Prerequisites

Make sure you have these installed BEFORE you start:

1. Docker
Install Docker: https://docs.docker.com/get-docker/
(This includes Docker Engine + Docker CLI)

2. Docker Compose
Comes bundled with Docker Desktop (Mac/Windows).
On Linux:
    sudo apt-get install docker-compose-plugin

-------------------------------------------

Steps to Run the Cydra App

1. Clone or Download the Project

If you haven’t already:

    git clone https://github.com/sowinskw/cydra-docker.git
    cd cydra-docker

Make sure you have the following structure:

    project-root/
    ├── docker-compose.yaml

-------------------------------------------

2. Pull the Docker Images

The docker-compose.yaml is set up to pull the latest backend and frontend images automatically:

- sowinskw/cydra-backend:latest
- sowinskw/cydra-frontend:latest

No need to build anything!

-------------------------------------------

3. Run the Application with Docker Compose

In the root of your project directory (where docker-compose.yaml is located), run:

    docker-compose up -d

What this does:

Downloads the backend and frontend images (if they aren't already)
Starts both services in detached mode (-d)
Backend listens on port 8080
Frontend listens on port 5173

-------------------------------------------

4. Check if Containers Are Running

    docker-compose ps

You should see something like:

    Name               Command               State           Ports
    ---------------------------------------------------------------------
    cydra-backend    python app.py              Up      0.0.0.0:8080->8080/tcp
    cydra-frontend   yarn dev --host 0.0.0.0    Up      0.0.0.0:5173->5173/tcp

-------------------------------------------

5. Access the Application

Frontend (UI): http://localhost:5173
Backend (API): http://localhost:8080

-------------------------------------------

6. Stop the App

To stop everything:

    docker-compose down

-------------------------------------------

Recap

What You Did:

- Pulled the latest Docker images
- Ran the backend and frontend containers on a Docker network
- Accessed the app via localhost

-------------------------------------------

Optional: Check Logs

You can view logs for either container:

    docker-compose logs -f backend

    docker-compose logs -f frontend

-------------------------------------------

Optional: Clean Up Images and Volumes

If you want to clean things completely:

    docker-compose down --volumes --rmi all

-------------------------------------------
-------------------------------------------

Happy containerizing!
