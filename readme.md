# Flask App with MySQL Docker Setup

This is a simple Flask app that interacts with a MySQL database. The app allows users to submit messages, which are then stored in the database and displayed on the frontend.

<img width="1704" height="617" alt="image" src="https://github.com/user-attachments/assets/058bee63-fa86-42d7-9972-e32f948d6e3e" />


## Prerequisites

Before you begin, make sure you have the following installed:

- Docker
- Git (optional, for cloning the repository)

## Setup

1. Clone this repository (if you haven't already):

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   ```
2. Navigate to the project directory:

   ```bash
   cd your-repo-name
   ```

3. Create a `.env` file in the project directory to store your MySQL environment variables:

   ```bash
   touch .env
   ```

4. Open the `.env` file and add your MySQL configuration:

   ```
   MYSQL_HOST=mysql
   MYSQL_USER=your_username
   MYSQL_PASSWORD=your_password
   MYSQL_DB=your_database
   ```
5. Install docker
   ```
   - sudo apt update
   - sudo apt install docker.io
   - sudo USERMOD -aG docker $USER & newgrp docker
   ```
6. Create a Dockerfile
   <img width="1745" height="989" alt="image" src="https://github.com/user-attachments/assets/7be7c712-b19c-4ddb-808e-bcfd2639ec5c" />

7. Build the image
   ```
   - docker build -t flasapp .
   ```
8. 

   
