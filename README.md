# RAG-using-Azure-Databricks-CI-CD

[Ayush Jayendra Patel](https://github.com/Ayush-Patel-10) [Bharath Raju Palla](https://github.com/BharathRajuPalla) [Harsha Bhargav Yarramsetty](https://github.com/Harsha-Bhargav) [Luv Verma](https://github.com/luv91) [Shivali Katharia](https://github.com/ShivaliKatharia) [Spandan Maaheshwari](https://github.com/s8m21)

# Introduction




![llmops_1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/717de3ce-02c2-4efc-acc2-42d6529bdf7c)




# Project Overview for RAG-using-Azure-Databricks-CI-CD

This repository houses the `RAG-using-Azure-Databricks-CI-CD` project, which demonstrates a comprehensive MLOps pipeline encompassing development, production, and monitoring within an Azure Databricks environment.


## Getting Started - Setup Guide

To begin working with the `RAG-using-Azure-Databricks-CI-CD` project, please follow the initial setup instructions detailed in the guide below:

- [Project Setup Guide on Azure & Databricks](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/SETUP.md)

This guide covers creating an Azure account, setting up resource groups, storage accounts, and Databricks workspaces, as well as configuring GitHub secrets and local development tools like the Databricks CLI.

After completing the initial setup, you can proceed to the detailed aspects of the project using the Table of Contents.

## Table of Contents

- [Azure & Databricks Setup Guide](#azure--databricks-setup-guide)
- [Databricks Folder Structure](#databricks-folder-structure)
- [Databricks Workflow](#databricks-workflow)
- [Terraform](#terraform)
- [CI/CD Workflow](#cicd-workflow)
- [Model Version Rollback](#model-version-rollback)
- [MLFlow](#mlflow)
- [Cost Analysis](#cost-analysis)


## Databricks Folder Structure

The project’s folder structure in Databricks is designed to separate files and artifacts across the test, staging, and prod environments, facilitating organized development and deployment.

[Understand our Databricks folder structure](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_DATABRICKS_FOLDER_STRUCTURE.md)


## Databricks Workflow

We maintain a detailed workflow for model training, evaluation, and deployment within Databricks, ensuring systematic testing and deployment of our models.

[Explore the Databricks workflow](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_DATABRICKS_WORKFLOW.md)


## Terraform

Terraform is used for infrastructure provisioning and state management within our Databricks environment.

[Review our Terraform practices](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_TERRAFORM_TFSTATE.md)


## CI/CD Workflow

Our project utilizes a CI/CD pipeline that orchestrates the workflow from development to staging and production. 

[Read more about the CI/CD workflow](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_CICD_WORKFLOW.md)


## Model Version Rollback

Our process for rolling back to previous model versions in production is documented to ensure reliability and ease of transitions.

[Learn about model version rollback](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_MODEL_VERSION_ROLLBACK.md)



## MLFlow

MLFlow is integral to our pipeline, providing tools for model versioning, management, and serving in both test and production environments.

[Read about our MLFlow setup](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_MLFlow.md)


## Cost Analysis

We conduct a thorough cost analysis to optimize resource allocation and manage expenses effectively.

[Delve into our cost analysis approach](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/blob/main/README/README_Cost_Analysis.md)









