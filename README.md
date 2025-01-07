
# ETL-Weather

ETL-Weather is an automated pipeline designed to extract, transform, and load weather data from the OpenWeather API into a PostgreSQL database. Leveraging Apache Airflow for orchestration, this project ensures efficient and reliable data processing, making it suitable for analysis and visualization tasks.

## Table of Contents

- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Technologies Used](#technologies-used)
- [Features](#features)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The primary objective of ETL-Weather is to automate the process of collecting weather data, transforming it into a structured format, and loading it into a PostgreSQL database. This automation facilitates seamless data analysis and visualization, aiding in decision-making processes that depend on accurate and up-to-date weather information.

## Architecture

The ETL pipeline comprises the following stages:

1. **Extraction**: Utilizes the OpenWeather API to fetch real-time weather data for specified locations.

2. **Transformation**: Processes the raw data to ensure consistency and accuracy, including unit conversions (e.g., temperature from Kelvin to Celsius) and timestamp adjustments.

3. **Loading**: Inserts the transformed data into a PostgreSQL database, ensuring efficient storage and retrieval for analysis.

Apache Airflow orchestrates these stages, managing task scheduling and execution to maintain data pipeline integrity.

## Technologies Used

- **Python**: Core programming language for data extraction and transformation.

- **Apache Airflow**: Orchestrates the ETL workflow, managing task dependencies and scheduling.

- **PostgreSQL**: Serves as the relational database for storing processed weather data.

- **Docker**: Ensures consistent deployment across various environments through containerization.

- **OpenWeather API**: Source of real-time weather data.

## Features

- **Automated Data Pipeline**: Fully automates the ETL process, reducing manual intervention.

- **Scalability**: Designed to handle large datasets, accommodating multiple locations and extended timeframes.

- **Data Integrity**: Implements validation checks to maintain data accuracy and consistency.

- **Extensibility**: Modular design allows for easy integration of additional data sources or transformation steps.

## Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/varunsonawane/ETL-Weather.git
   cd ETL-Weather
   ```

2. **Configure Environment Variables**:
   - Create a `.env` file in the project root directory.
   - Add the following variables:
     ```env
     OPENWEATHER_API_KEY=your_openweather_api_key
     POSTGRES_USER=your_postgres_username
     POSTGRES_PASSWORD=your_postgres_password
     POSTGRES_DB=your_database_name
     POSTGRES_HOST=your_postgres_host
     POSTGRES_PORT=your_postgres_port
     ```

3. **Set Up Docker Environment**:
   - Ensure Docker is installed and running on your machine.
   - Build and start the Docker containers:
     ```bash
     docker-compose up --build
     ```

4. **Initialize Airflow**:
   - Access the Airflow web interface at `http://localhost:8080`.
   - Create necessary connections for the OpenWeather API and PostgreSQL database.

5. **Trigger the ETL Pipeline**:
   - In the Airflow web interface, locate the `etl_weather_pipeline` DAG.
   - Trigger the DAG manually or set it to run on a schedule.

## Usage

Once the ETL pipeline is operational, it will regularly fetch and process weather data, storing it in the PostgreSQL database. This data can be accessed for various analytical purposes, such as:

- **Data Analysis**: Perform statistical analyses to identify weather trends and patterns.

- **Visualization**: Create dashboards or visual reports to represent weather data graphically.

- **Machine Learning**: Develop predictive models based on historical weather data.


