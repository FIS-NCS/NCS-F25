# Network & Cyber Security - Fall 2025

## Content

- Lab 1: Security Compliance

## Instructions

1. Ensure you have docker and docker compose plugin installed

   ```bash
   docker -v
   docker compose version
   ```

2. Clone this repository

   ```bash
   git clone https://github.com/FIS-NCS/NCS-F25
   ```

3. Change into the project directory

   ```bash
   cd NCS-F25
   ```

4. Fix permissions of the recordings directory
   > Minimum permissions required: to be writable by container user (id=1001) and readable by host.

   ```bash
   sudo chmod 777 recordings
   ```

5. Stop previous container instances (if any)

   ```bash
   docker kill terminal renderer nginx
   docker container prune -f
   ```

6. [Before running any lab] Ensure you have the latest changes.

   ```bash
   git pull
   docker compose pull
   ```

7. Update `docker-compose.yaml` to serve lab files 

   ```yaml
   services:
      ...
      renderer:
        volumes:
         - ./<DIR_OF_MD_FILES>:/opt/renderer/workshop/content
   ```

8. Run the environment

   ```bash
   docker compose up -d
   ```

9. Access the lab at <http://localhost:8080>
