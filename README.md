## How to Recreate This Project Step by Step

1. Create a new folder called `coderco-challenge`.
2. Inside that folder, create these files:
   - `count.py` – Flask app that talks to Redis
   - `Dockerfile` – builds the Python image
   - `docker-compose.yml` – defines the `web` and `redis` services
   - `requirements.txt` – lists Python dependencies
3. Install Docker Desktop and make sure the Docker engine is running.
4. Open the folder in VS Code.
5. Build and start everything with Docker Compose:

   docker compose up --build

6. Once both containers are running, open:
   - `http://localhost:5002/` → welcome page
   - `http://localhost:5002/count` → visit counter backed by Redis
7. Stop and clean up the containers when you’re done:

   docker compose down -v

---

## Common Pitfalls (and How to Avoid Them)

1. **Python indentation errors**

   If a function in `count.py` isn’t indented correctly, the container will crash on start.
   - Tip: make sure each function body is indented with 4 spaces under the `def` line.

2. **App file in the wrong place**

   Docker needs to find `count.py` inside the same folder as the `Dockerfile` and `docker-compose.yml`.
   - Tip: confirm the structure looks like:

     coderco-challenge/  
     ├─ count.py  
     ├─ Dockerfile  
     ├─ docker-compose.yml  
     ├─ requirements.txt  

3. **Docker engine not running**

   If `docker compose up` hangs or fails immediately, Docker Desktop might not be running.
   - Tip: open Docker Desktop first and check that it says “Engine running” before using the terminal.
