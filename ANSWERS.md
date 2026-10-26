HW-2 Answers

1. Your app calls the second service by name. How does that work, and why does the same name not work between two containers on the default docker run network?

Docker Compose lets containers find each other using service names through its network. In our project, the app connects to PostgreSQL using db as the hostname. The default docker run bridge network does not provide the same automatic name resolution between containers.

2. Which of your services is stateless and which is not? Show the evidence: what did you do, and what happened to your data (for example docker compose rm -sf app and then docker compose down, and docker compose down -v)?

The app is stateless, while PostgreSQL is stateful because it stores the task data. After docker compose rm -sf app and docker compose down, both tasks were still available. After docker compose down -v, the tasks disappeared because the database volume was deleted.

3. Where should a database password come from, and why is it a problem to commit it to Git, even in a private repository?

The database password should come from a local .env file or environment variable. The .env file should be excluded from Git, while .env.example can contain example values. Committing a real password is risky because someone could gain access to the database if the repository or credentials are exposed.

AI Use Statement

I used ChatGPT to help understand Docker concepts and organize my answers. I ran the commands and checked the results myself.