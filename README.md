🛠 How to Run the Project
1️⃣ Build & Start the Containers

From inside the project folder (coderco-challenge), run:

docker compose up --build


This will:

Build the Flask app image

Start the Redis container

Start the Flask container

Bind port 5002 → your browser

2️⃣ Access the App

Open your browser:

http://localhost:5002/

http://localhost:5002/count

🧪 What We Tested

✔️ Flask app runs inside its own container
✔️ Redis stores visit counter
✔️ Both containers communicate through a Docker network
✔️ /count increases every time you refresh the page

🐞 Errors & Challenges We Faced
1. IndentationError in count.py

Python functions weren't indented properly.

Solution: rewrote the file cleanly with correct spacing.

2. count.py was in the wrong folder

Docker couldn’t find the file (because it was outside coderco-challenge/)

Solution: moved it into the correct folder.

3. Docker Engine was not running

docker compose commands were freezing with no output.

Solution: updated Docker Desktop + restarted the engine.

4. touch does not work on Windows PowerShell

PowerShell does not support the Linux touch command.

Solution: created README.md using VS Code instead.

📁 Project Structure
coderco-challenge/
│   count.py
│   Dockerfile
│   docker-compose.yml
│   requirements.txt
│   README.md
