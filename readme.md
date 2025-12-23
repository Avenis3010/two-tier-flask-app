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
8. run the conatiner using:
   ```
   - docker run -d -p 5000:5000 flaskapp:latest
   ```
9. open 5000 port on instance SG, and try access it in browser
10. we have to run the mysql container as well.
    ```
    - docker run -d -p 3306:3306 mysql:5.7
    ```
11. run the containers  include env variables and create the network.
    ```
    - docker network create two-tier
    ```
12. run the mysql and flaskapp containers in the same network.
    ```
    - docker run -d -p 3306:3306 --network=two-tier -e MYSQL_DATABASE=myDb -e MYSQL_USER=admin -e MYSQL_PASSWL_USER=admin -e                        MYSQL_PASSWORD=admin -e MYSQL_ROOT_PASSWORD=admin --name=mysql mysql:5.7
    - docker run -d -p 5000:5000 --network=two-tier -e MYSQL_HOST=mysql -e MYSQL_USER=admin -e MYSQL_PASSWORD=admin -e MYSQL_DB=myDb --             name=flaskapp flaskapp:latest
    ```
13. TRY TO ACCESS the application on browser.
14.  Go inside the mysql container
    
    ```
     - docker exec -it (mysql-container-id)
     -  mysql -u root -p\
     -  enter password
     -  show databases;
     -  use myDb;
     -  CREATE TABLE message(id INT AUTO_INCREMENT PRIMARY KEY, message TEXT);
     -  select * from message;
     ```
15. access the applicatio n on browser on port 5000.
       
     <img width="1283" height="838" alt="image" src="https://github.com/user-attachments/assets/c823300e-3ce3-4f7c-ad37-ecd3133ce375" />

    

   
