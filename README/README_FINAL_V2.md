#





![Shivali - Azure framework](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/732afefe-5074-4b3e-82c0-0a1c676814fe)

![Blank diagram (5)](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/5aa6d8b3-5f8d-4bd3-b75e-2a2451e2c577)

# Project Overview for my_mlops_project_luv_v6

This repository houses the `my_mlops_project_luv_v6` project, which demonstrates a comprehensive MLOps pipeline encompassing development, production, and monitoring within an Azure Databricks environment.

## Getting Started
To begin working with the `my_mlops_project_luv_v6` project, please follow the initial setup instructions detailed in the guide below:

- [Project Setup Guide on Azure & Databricks](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/SETUP.md)

This guide covers creating an Azure account, setting up resource groups, storage accounts, and Databricks workspaces, as well as configuring GitHub secrets and local development tools like the Databricks CLI.


After completing the initial setup, you can proceed to the detailed aspects of the project using the Table of Contents.

## Table of Contents
- [CI/CD Workflow](#cicd-workflow)
- [Cost Analysis](#cost-analysis)
- [Databricks Folder Structure](#databricks-folder-structure)
- [Databricks Workflow](#databricks-workflow)
- [Model Version Rollback](#model-version-rollback)
- [MLFlow](#mlflow)
- [Terraform](#terraform)
- [Notebook Configurations](#notebook-configurations)
- [Data Ingestion Pipeline](#data-ingestion-pipeline)
- [Advanced Chatbot Chain](#advanced-chatbot-chain)
- [Offline Evaluation](#offline-evaluation)
- [Model Deployment](#model-deployment)
- [Inference Table Analysis](#inference-table-analysis)
- [Azure & Databricks Setup Guide](#azure--databricks-setup-guide)

## CI/CD Workflow
Our project utilizes a CI/CD pipeline that orchestrates the workflow from development to staging and production. 

[Read more about the CI/CD workflow](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_CICD_WORKFLOW.md)

## Cost Analysis
We conduct a thorough cost analysis to optimize resource allocation and manage expenses effectively.

[Delve into our cost analysis approach](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_Cost_Analysis.md)

## Databricks Folder Structure
The project’s folder structure in Databricks is designed to separate files and artifacts across the test, staging, and prod environments, facilitating organized development and deployment.

[Understand our Databricks folder structure](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_DATABRICKS_FOLDER_STRUCTURE.md)

## Databricks Workflow
We maintain a detailed workflow for model training, evaluation, and deployment within Databricks, ensuring systematic testing and deployment of our models.

[Explore the Databricks workflow](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_DATABRICKS_WORKFLOW.md)

## Model Version Rollback
Our process for rolling back to previous model versions in production is documented to ensure reliability and ease of transitions.

[Learn about model version rollback](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_MODEL_VERSION_ROLLBACK.md)

## MLFlow
MLFlow is integral to our pipeline, providing tools for model versioning, management, and serving in both test and production environments.

[Read about our MLFlow setup](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_MLFlow.md)

## Terraform
Terraform is used for infrastructure provisioning and state management within our Databricks environment.

[Review our Terraform practices](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_TERRAFORM_TFSTATE.md)

## Notebook Configurations
A series of notebooks are utilized for configuration and initialization, forming the backbone of our chatbot project.

- [Config Notebook](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_init_config.md)
- [Initialization Notebooks](#initialization-notebooks)

## Data Ingestion Pipeline
Our data ingestion pipeline efficiently handles the flow from file upload to content extraction and embedding computation, ultimately enabling similarity search and retrieval.

[See our data ingestion pipeline steps](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_notebook_1.md)

## Advanced Chatbot Chain
The advanced chatbot chain leverages Langchain to enhance the chatbot's interactions and processing capabilities.

[Understand the Advanced Chatbot Chain](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_notebook_2.md)

## Offline Evaluation
We perform offline evaluations of our chatbot using rigorous testing and validation to ensure production readiness.

[Discover our offline evaluation process](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_notebook_3.md)

## Model Deployment
Learn the detailed steps for model deployment and endpoint creation within our project infrastructure.

[Guide to model deployment](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_notebook_4.md)

## Inference Table Analysis
Databricks Lakehouse Monitoring is employed to track performance metrics, ensuring the model’s quality over time.

[Analyzing inference tables](https://github.com/luv91/my_mlops_project_luv_v6/blob/read/README/README_notebook_5.md)
