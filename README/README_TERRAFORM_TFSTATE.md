# Terraform State Overview for the my_mlops_project_luv_v6 Project

## Introduction
This document delineates the Terraform state management for the `my_mlops_project_luv_v6` project. It covers resource management and infrastructure provisioning within the Databricks environment.

## Terraform Details
- **Version**: 1.5.5
- **State File Serial Number**: 7
- **Lineage Identifier**: 8ac9ae2e-dc90-fc6f-07e9-e0a885d24582

The Terraform state file (`terraform.tfstate`) is pivotal for tracking the state of resources, their metadata, and the configuration mapping to the real-world cloud environment.

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/24a97ff3-1e7e-4c49-b3eb-923d54c1000f)


## Managed Resources

### Databricks Grants
- **Type**: `databricks_grants`
- **Name**: `registered_model_model`
- **Function**: Grants EXECUTE privileges on the model's associated function to `account users`.

### Databricks Jobs
#### Batch Inference Job
- **Type**: `databricks_job`
- **Name**: `batch_inference_job`
- **Description**: Orchestrates batch inference tasks using a specified bundle.

#### Model Training Job
- **Type**: `databricks_job`
- **Name**: `model_training_job`
- **Description**: Sequentially manages model training tasks upon successful completion of predecessors.

### Databricks MLflow Experiment
- **Type**: `databricks_mlflow_experiment`
- **Name**: `experiment`
- **Description**: Manages MLflow experiments for artifact and data tracking.

### Databricks Permissions
- **Type**: `databricks_permissions`
- **Name**: `mlflow_experiment_experiment`
- **Description**: Provides CAN_READ access to the `users` group for the MLflow experiment.

### Databricks Registered Model
- **Type**: `databricks_registered_model`
- **Name**: `model`
- **Description**: Manages a model in Unity Catalog designated for production.

## Infrastructure Provisioning

- **Storage Location**: Specifies the Azure Blob storage location for the model's data.
- **Cluster ID**: Identifies the cluster for the batch inference job execution.

## Metadata and Deployment

- **Metadata File Path**: `/Users/maaheshwarispandan97@outlook.com/.bundle/my_mlops_project_luv_v6/prod/state/metadata.json`
- **Model Function Identifier**: `prod.my_mlops_project_luv_v6.my_mlops_project_luv_v6-model`

## Additional Notes

The Terraform state ensures synchronization between expected and real configurations, conflict prevention through state locking, and tracking of resource dependencies for orderly management.

## Resource Relationships

The state file encapsulates not only the state of resources but also the dependencies between them, ensuring orderly creation, update, and deletion processes.
