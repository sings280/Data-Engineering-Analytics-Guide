ETL Pipelines
ETL (Extract, Transform, Load) pipelines are critical for moving data from sources to destinations while applying necessary transformations.
DAG Example with Apache Airflow
Below is a Mermaid diagram showing a simple ETL pipeline DAG (Directed Acyclic Graph).
graph TD
    A[Extract from API] --> B[Transform Data]
    B --> C[Load to Warehouse]
    C --> D[Validate Data]
    D --> E[Notify Success]

Sample Airflow DAG Code
from airflow import DAG
from airflow.operators.python import PythonOperator
from datetime import datetime

def extract():
    print("Extracting data from API...")
def transform():
    print("Transforming data...")
def load():
    print("Loading to warehouse...")

with DAG('etl_pipeline', start_date=datetime(2025, 1, 1), schedule_interval='@daily') as dag:
    extract_task = PythonOperator(task_id='extract', python_callable=extract)
    transform_task = PythonOperator(task_id='transform', python_callable=transform)
    load_task = PythonOperator(task_id='load', python_callable=load)
    
    extract_task >> transform_task >> load_task

This code defines a basic Airflow DAG with three tasks: extract, transform, and load.