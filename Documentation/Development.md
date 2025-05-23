# Vote Vault

This project used php with Laravel 11 & PostgreSQL 16, see below instructions to replicate a local environment for testing.

## Install Prerequisites

### Install Docker Desktop
- Install Docker Desktop on your machine from this [documentation](https://docs.docker.com/get-started/get-docker/) or the link below.
  - [Mac](https://docs.docker.com/desktop/install/mac-install/)
  - [Windows](https://docs.docker.com/desktop/install/windows-install/)
  - [Linux](https://docs.docker.com/desktop/install/linux/)

### Setup Directory
- Make sure you're under **VoteVault** folder
- Clone the following repositories in that folder
  - https://github.com/KyuXCode/vote-vault-frontend
  - https://github.com/KyuXCode/vote-vault-api
- You can do it via command line:
  - Right-click on the VoteVault folder and select **New Terminal at Folder** or **Shift+Right-click** to an empty place on that folder to open a command line for Windows. ![Folder dropdown menu](./InstructionScreenshots/folder_dropdown_menu.png)
  - Run these commands (it assumes you have git installed and git command accessible in PATH environment variable): 
   ```
   git clone https://github.com/KyuXCode/vote-vault-api.git
   git clone https://github.com/KyuXCode/vote-vault-frontend.git
   ```
  - Your folder should be something like this with ```vote-vault-api``` & ```vote-vault-frontend``` in your ```VoteVault``` folder. ![folder after cloning](./InstructionScreenshots/folder_after_cloning.png)
- Open the Docker Desktop app before the next stage ![Docker Desktop Logo](./InstructionScreenshots/Docker_Desktop_logo.png)

## Start the Project Locally
### 1. Make sure you start the ```vote-vault-api``` first.
Make sure you're in the ```vote-vault-api``` directory 
```
cd vote-vault-api
```
- Only run the command below on the first time you run the docker container or if you made any changes in the api code
    ```
    docker compose up --build
    ```

- Run the command below to stop the container
    ```
    docker compose down
    ```

- Run this to restart (unless you made changes)
    ```
    docker compose up 
    ```
Go to your browser and enter this link: [http://127.0.0.1:8000/](http://127.0.0.1:8000/), you should see a default Laravel page ![Laravel Index Page](./InstructionScreenshots/laravel_landing_page.png)

### 2. Then start ```vote-vault-frontend```
Make sure you're in the ```vote-vault-frontend``` directory
```
cd ..
cd vote-vault-frontend
```
Start the docker container for the frontend. (You only have to run this command once, the frontend is setup for hot-reload)
```
docker compose up --build
```
- Run the command below to stop the container
    ```
    docker compose down
    ```

- Run this to restart
    ```
    docker compose up 
    ```
Go to your browser and enter this link: [http://127.0.0.1:3000/](http://127.0.0.1:3000/), you should see the React frontend. ![Frontend Index Page](./InstructionScreenshots/vote_vault_frontend.png)

## Testing
### Backend Testing
We're using phpunit test for this project which is located under the tests folder
- To run the existing tests open docker desktop and click on ```vote_vault_dev``` ![Open Docker Image](./InstructionScreenshots/select_docker_image.png)
- Select the Exec tab to open terminal of the image ![Open Docker Terminal](./InstructionScreenshots/select_image_terminal.png)
- Run the following command
    ```
    php artisan test --parallel
    ```
- If you need data to test, run the following for seeders, it will generate data for you
  ```
  php artisan db:seed
  ```
- You should see if they passed or not ![Test Result](./InstructionScreenshots/Test_result.png)
### Frontend Testing
We're using vite test for frontend testing
- To run existing tests, enter the command ```npm test```

## Common Errors
### Error 1: Connection to server at "postgresql" failed: connection refused 
- Sometimes ```vote_vault_dev``` image finish before ```postgres-db``` image which will throw the error like below when you ran ```docker compose up --build``` in ```vote-vault-api``` folder. ![docker issue](./InstructionScreenshots/docker_starting_order_issue.png)
- **Solution 1:** Go to docker decktop and find your ```vote-vault-api``` container and start the ```vote_vault_dev``` image again by clicking the highlighted play button ![Restart Docker Image](./InstructionScreenshots/restart_docker_image.png)
- **Solution 2:** sometime your local port at ```5432``` is taken so the container couldn't use the port to connect to the PostgreSQL database, run the following command (or equivalent on window) to check if the port is currently in use
- In your terminal, do this to see if it's in used
  ```
  sudo lsof -i :5432
  ```
  ![pid example](./InstructionScreenshots/pid_example.png)
- Kill all the processes that are running under this port
  ```
  sudo kill -9 <pid>
  ```
- Run the command again to verify no process is running now
  ```
  sudo lsof -i :5432
  ```

## Testing
### Running in terminal locally
- Run test in terminal
  ```
  vitest
  ```
- Run coverage in terminal
  ```
  vitest run --coverage
  ```

### Running in docker container
1. Make sure your project is up to date
2. Start the docker container
3. Go to the container and select exec
4. Run the following in the docker terminal
- Run test in terminal
  ```
  npm run test
  ```
- Run coverage in terminal
  ```
  npm run coverage
  ```