# Databricks Workflow Documentation

This document provides an overview of the workflow, timeline, and lineage of the model training job in the production and test environment of the `prod-my_mlops_project_luv_v6` project within Databricks. The workflow is the same but happens with just 1 file (pdf) to test for the unit and integration tests in the Test environment.

## Workflow Overview

The workflow is composed of a sequence of tasks, each representing a step in the model training process. The tasks are executed in a predefined order, ensuring that each step is completed before the next one begins.

## Workflow Graph

The workflow graph provides a visual representation of the job run, displaying the interconnected tasks and their execution status.

### Tasks and Status

- `01-PDF-Advance-Data-Preprocessing`: Processes and prepares PDF data for modeling.
- `02-Advanced-Chatbot-Chain`: Trains the advanced chatbot model.
- `03-Offline-Evaluation`: Evaluates the model in a simulated offline environment.
- `04-Deploy-Model-As-Endpoint`: Deploys the model as an endpoint for production use.

All tasks have succeeded, indicating a successful run of the workflow (see the figure below):

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/cfefc8a0-1a6c-4302-8d34-b1a189581408)

## Timeline View

The timeline view offers a chronological view of the job run, showing the duration of each task.

- The `PDF-Advance-Data-Preprocessing` task took 7m 50s.
- The `Advanced-Chatbot-Chain` task took 57s.
- The `Offline-Evaluation` task took 3m 25s.
- The `Deploy-Model-As-Endpoint` task took 17m 18s.

(see the figure below):

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/29aa6114-6924-45aa-b15b-bc6274056c8a)

## Job Run Details

- **Job ID**: 863140283668241
- **Job Run ID**: 657341104998666
- **Launched**: Manually
- **Started**: 04/19/2024, 05:54:15 PM
- **Ended**: 04/19/2024, 06:23:46 PM
- **Duration**: 29m 32s

## Lineage

The job run includes lineage tracking, which details the relationship between upstream and downstream tables processed during the job.

- **Upstream Tables**: 3 tables that provided input to the job.
- **Downstream Tables**: 3 tables that were populated as a result of the job run.

## Compute Details

- **Cluster**: maaheshwarispandan97@outlook.com's Cluster
- **Node Type**: Single node: Standard_D3_v2 - 12.2 LTS ML (includes Apache Spark 3.3.2, Scala 2.12)

(see the figure below):

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/528e2c90-0626-443e-b573-44b2a311e9d3)



