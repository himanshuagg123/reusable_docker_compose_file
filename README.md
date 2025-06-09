# Reusable Docker Compose for Django Project

This project demonstrates how to set up a **basic Django application** with **PostgreSQL** database using **Docker Compose**. The setup is designed to be reusable and easy to extend for testing and development.

---

## 🚀 What You Will Learn

- How to containerize a Django app using Docker.
- How to use Docker Compose to run multiple containers (Django + PostgreSQL).
- How to manage environment variables with `.env` file.
- How to create a reusable Docker Compose file for tests.
- How to run migrations and start the Django server inside containers.

---

## 📁 Project Structure

myproject/
│
├── docker-compose.yml # Base Docker Compose file with app + db services
├── docker-compose.test.yml # Docker Compose file for testing (extends base)
├── Dockerfile # Dockerfile for building Django app image
├── .env # Environment variables file (DB credentials)
├── myproject/ # Django project folder
│ ├── settings.py
│ └── ...
└── README.md # This file

yaml
Copy
Edit

---

## 🧰 Prerequisites

- Docker installed on your machine
- Basic knowledge of Django and Docker

---

## ▶️ How to Run the Project

1. **Clone the repository**

```bash
git clone <your-repo-url>
cd myproject
Create .env file

Create a .env file in the project root with these variables:


POSTGRES_DB=yourdbname
POSTGRES_USER=yourdbuser
POSTGRES_PASSWORD=yourdbpassword
Build and start containers


docker-compose up --build
Apply migrations

Open another terminal and run:


docker-compose exec web python manage.py migrate
Access the Django app

Visit http://localhost:8000 in your browser.

🧪 How to Run Tests

docker-compose -f docker-compose.yml -f docker-compose.test.yml up --abort-on-container-exit
This will run your Django tests and stop the containers after the test container exits.

♻️ Why Reusable Docker Compose?
Keeps dev and test environments separate

Easy to override or extend services

Ensures consistent environments across machines

Clean and modular setup

🛠️ Troubleshooting
❗Missing Service Error: Use both YAML files with -f when testing.

❗Port already in use: Update the port in docker-compose.yml.

❗Docker not running: Make sure Docker Desktop or Engine is up.

🤝 Contributing
Pull requests and feedback are welcome! Let’s improve it together.

📄 License
This project is open source and free to use.

