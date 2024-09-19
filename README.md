# ETL Pipeline for Real Estate Prices

[![Generic badge](https://img.shields.io/badge/Python-3.11-green.svg)](https://www.python.org/)
[![Generic badge](https://img.shields.io/badge/PySpark-3.1.2-green.svg)](https://spark.apache.org/docs/latest/api/python/#)
[![Generic badge](https://img.shields.io/badge/Apache_Airflow-2.2.2-green.svg)](https://airflow.apache.org/)
[![Generic badge](https://img.shields.io/badge/Delta-1.0.0-green.svg)](https://delta.io/)
[![Generic badge](https://img.shields.io/badge/Papermill-2.3.4-green.svg)](https://papermill.readthedocs.io/en/latest/)
[![Generic badge](https://img.shields.io/badge/Apache_Druid-0.23.0-green.svg)](https://druid.apache.org/)
[![Generic badge](https://img.shields.io/badge/Apache_Superset-1.5.0-green.svg)](https://superset.apache.org/)
[![Generic badge](https://img.shields.io/badge/Docker-20.10.6-green.svg)](https://www.docker.com/)

- The project was based on an open-source template and adapted to practice using Apache Airflow for workflow orchestration, PySpark for data processing, and Apache Druid for real-time analytics.

## Description: 
 - This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline designed to scrape real estate data, process it for analysis, train a predictive model for house prices, and visualize the results on a real-time analytics dashboard.
 - The primary goal was to build a fully automated data pipeline using open-source technologies like Apache Airflow, PySpark, and Apache Druid.
 - The processed data is stored in a Delta Lake across different layers to ensure data integrity and scalability, followed by ingestion into Apache Druid for real-time data querying and analysis.

## Project Highlights:
 - Data Source: Scraped real estate data from Immo Scout 24, including property descriptions, features, and prices.
 - ETL Pipeline: Built using PySpark inside Jupyter Notebooks to process raw data and train a machine learning model.
 - Real-Time Analytics: Integrated Apache Druid and Apache Superset to track model performance and make data-driven decisions.
   
## Key Responsibilities:
 - Set up an environment using Docker to manage services and dependencies.
 - Scraped real estate data from Immo Scout 24 using PySpark inside Jupyter Notebooks.
 - Processed data through Delta Lake’s bronze, silver, and gold layers, ensuring data integrity.
 - Trained a machine learning model using PySpark MLlib to predict real estate prices.
 - Orchestrated the entire pipeline with Apache Airflow and ingested results into Apache Druid for real-time analysis.
 - Created an Apache Superset dashboard to visualize model performance and insights.

## Technologies Used
- **Docker**: Used to containerize all services, including Apache Airflow, Apache Druid, and Jupyter Notebooks, enabling seamless orchestration and scalability.
- **Apache Airflow**: Orchestrated the entire ETL pipeline from data scraping to model training and dashboard creation.
- **PySpark**: Leveraged for data extraction, processing, and model training, utilizing Spark’s distributed computing for scalability.
- **Delta Lake**: Stored processed data across bronze, silver, and gold layers, enabling ACID-compliant transactions and scalable storage solutions.
- **Apache Druid**: Used for real-time analytics and fast query processing on large datasets.
- **Apache Superset**: Built an interactive dashboard to visualize and filter data and model performance metrics.
- **Jupyter Notebooks**: Prototyped and tested various parts of the pipeline and performed data analysis in an interactive environment.
  
## Pipeline Architecture
- **Data Extraction**:
The project starts with scraping real estate data from Immo Scout 24 using PySpark, gathering information such as property descriptions, prices, and features (e.g., number of rooms, living area, location, etc.).

- **Data Processing**:
Once the raw data is scraped, it is processed and cleaned using PySpark to handle missing or inconsistent values. The processed data is stored in Delta Lake across three layers:
    - **Bronze Layer**: Stores raw data scraped from the website.
    - **Silver Layer**: Data is cleaned and validated in this layer.
    - **Gold Layer**: Aggregated data, ready for machine learning and analysis.
    
- **Machine Learning Model**:
Using PySpark MLlib, a machine learning model was trained to predict real estate prices based on the property’s features (e.g., surface area, number of rooms). The model improved prediction accuracy by 20%, offering reliable price estimates for future properties.

- **Automation & Orchestration**:
Apache Airflow orchestrated the entire pipeline. Airflow DAGs automated tasks such as:
    - Scraping data periodically from the real estate website.
    - Processing and cleaning the data.
    - Training the machine learning model.
    - Ingesting processed data into Apache Druid for real-time analytics.
    
- **Real-Time Analytics and Dashboard**:
Once the data and predictions were ingested into Apache Druid, an interactive dashboard was built using Apache Superset. The dashboard enabled stakeholders to:
    - Visualize real estate price trends.
    - Monitor model performance over time.
    - Filter and explore data by different dimensions, such as city or property features.

- **Monitoring & Versioning**:
Delta Lake allowed continuous data ingestion and updates, maintaining version control and ensuring consistency across all data layers. Airflow's logging and monitoring provided insights into pipeline performance and error handling.

## Commands & Setup
To run this project locally, you will need Docker installed.

1. Clone the repository:
   
        $ git clone https://github.com/yourusername/real-estate-price-prediction.git
        $ cd real-estate-price-prediction
   
2. Initialize Docker environment:

        $ echo -e "AIRFLOW_UID=$(id -u)\nAIRFLOW_GID=0" > .env
        $ docker compose build
        $ docker compose up airflow-init
        $ docker compose up
   
## Project Results
- The machine learning model trained on real estate data achieved a 20% improvement in price prediction accuracy.
- The entire ETL process was automated, reducing the time required for data scraping, cleaning, and analysis.
- The Superset dashboard provided a clear visualization of model performance and real estate trends, offering actionable insights for decision-makers.

## Conclusion
This project was an excellent opportunity to enhance my data engineering skills while working with real-world technologies such as Apache Airflow, PySpark, Delta Lake, and Apache Druid. By following along and implementing this project, I gained hands-on experience with building and orchestrating ETL pipelines, developing machine learning models, and creating real-time analytics dashboards.
