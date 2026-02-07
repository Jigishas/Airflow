# Airflow Data Engineering Project

This repository contains an Apache Airflow setup for data engineering workflows, configured to run in a Docker environment.

## Project Structure

- `docker-compose.yml`: Defines the Airflow service using Docker Compose.
- `Dockerfile`: Builds the custom Airflow image with additional dependencies (e.g., git).
- `airflow/`: Directory containing Airflow configuration and DAGs.
  - `airflow.cfg`: Airflow configuration file.
  - `dags/`: Directory for DAG (Directed Acyclic Graph) files.
    - `greet_python.py`: A simple DAG for greeting.
    - `my_first_airflow_dag.py`: Introductory DAG example.
    - `new_dag.py`: Another DAG example.
    - `New_learning_dag.py`: Learning-focused DAG.
    - `Welcome_dag.py`: DAG that prints welcome messages and dates.
  - `logs/`: Directory for Airflow execution logs.
  - Other Airflow-related files (e.g., database, auth manager).

## Prerequisites

- Docker installed on your system.
- Docker Compose installed.

## Setup and Running

1. **Clone or Download the Repository**:
   - Ensure you have the project files in your local directory.

2. **Build the Docker Image** (if not using a pre-built image):
   ```
   docker build -t airflow .
   ```

3. **Start the Airflow Services**:
   ```
   docker-compose up
   ```
   This command will start the Airflow webserver and scheduler in standalone mode.

4. **Access the Airflow UI**:
   - Open your browser and navigate to `http://localhost:8080`.
   - Use the credentials generated during the first run (check the console output or logs for login details).

5. **Stop the Services**:
   - Press `Ctrl+C` in the terminal to stop the services.
   - Or run `docker-compose down` to stop and remove containers.

## DAG Descriptions

- **welcome_dag**: A scheduled DAG that runs daily at 23:00. It includes tasks to print a welcome message and the current date.
- **my_first_airflow_dag**: An introductory DAG demonstrating basic Airflow concepts.
- **New_learning_dag**: A DAG for learning purposes (check the file for specific tasks).
- Other DAGs: Explore the `dags/` directory for additional workflows.

## Notes

- The project uses Apache Airflow's standalone mode for simplicity.
- Logs are stored in the `airflow/logs/` directory for debugging and monitoring.
- Ensure Docker Desktop is running if on Windows.

## Troubleshooting

- If the image 'airflow' is not found, ensure the Dockerfile is in the same directory and build it as described.
- Check Docker logs with `docker-compose logs` for any errors.
- For Airflow-specific issues, refer to the official [Airflow Documentation](https://airflow.apache.org/docs/).
