# Databricks Workflow Documentation

This document provides an overview of the workflow, timeline, and lineage of the model training job in the production and test environment of the `prod-LLMOps` project within Databricks. The workflow is the same but happens with just 1 file (pdf) to test for the unit and integration tests in the Test environment.

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

![1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/8402f24e-ae0c-459c-8ac6-9a2a74e50bec)


## Timeline View

The timeline view offers a chronological view of the job run, showing the duration of each task.

- The `PDF-Advance-Data-Preprocessing` task took 7m 50s.
- The `Advanced-Chatbot-Chain` task took 57s.
- The `Offline-Evaluation` task took 3m 25s.
- The `Deploy-Model-As-Endpoint` task took 17m 18s.

(see the figure below):

![2](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/672e9abd-9688-480e-8ba6-208b7fa6dafa)


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

- **Node Type**: Single node: Standard_D3_v2 - 12.2 LTS ML (includes Apache Spark 3.3.2, Scala 2.12)

(see the figure below):

![3](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/09773868-6d2b-4d2d-b99d-a73398611110)




