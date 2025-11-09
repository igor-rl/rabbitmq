# RabbitMQ on Docker - Shared Development Environment

This project sets up an optimized RabbitMQ environment for local
development, using a single container accessible by any project on the
host machine. The goal is to reduce resource usage by avoiding multiple
database instances for different applications.

Additionally, this project can serve as a base for creating your own
RabbitMQ image for production environments.

## 🚀 Features

-   **Single Container**: One shared RabbitMQ instance for all local
    projects.
-   **Data Persistence**: Stores data locally in the `./db` directory.
-   **Simplified Access**: Connect via `host.docker.internal`, allowing
    any local application to use the broker.
-   **Optimized for Development**: Based on the lightweight
    `postgres:16-alpine` image.
-   **Auto Restart**: The container automatically restarts in case of
    failure.

## 🔧 How to Use

### 1️⃣ Clone the Repository

Clone the project from GitHub:

``` sh
git clone https://github.com/igor-rl/postgresql.git
cd postgresql
```

### 2️⃣ Start the Container

Run the following command to start RabbitMQ:

``` sh
docker-compose up -d
```

### 3️⃣ Access the Dashboard

Host: <http://localhost:15672> `<br/>`{=html} User: `guest`
`<br/>`{=html} Password: `guest`

### 4️⃣ Configure `host.docker.internal` for Windows (optional)

If you're using WSL on Windows and `host.docker.internal` doesn't work,
follow these steps:

1.  Open the hosts file with a text editor as Administrator:

    -   Path: `C:\Windows\System32\drivers\etc\hosts`

2.  Add the following line at the end of the file:

    ``` txt
    127.0.0.1 host.docker.internal
    ```

3.  Save the file and close the editor.

This ensures that local traffic is properly routed to the RabbitMQ
container.

### 5️⃣ Stop the Container

To stop the container without removing it:

``` sh
docker-compose stop
```

### 6️⃣ Remove the Container

If you want to completely remove the container:

``` sh
docker-compose down
```

<br/>

---
<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-Igor_Lage-blue?style=social&logo=github)](https://github.com/igor-rl) 
![Static Badge](https://img.shields.io/badge/11--03--2025-black)


</div>
