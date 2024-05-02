## MLFlow Overview in Test Environment

MLFlow is an integral part of our MLOps pipeline, providing model versioning, management, and serving capabilities. This document outlines the key aspects of MLFlow operations within the test environment, detailing version controls, artifact handling, and how to utilize the models within the Databricks environment.

### Registered Models in Test Environment

Our MLFlow setup includes several versions of the model, with detailed tracking of experiments and model performance metrics.

![1__#$!@%!#__Pasted Graphic 1](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/a708fd0f-0af6-412e-a061-2afdff863018)

![1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/c1107b7b-9ddd-4dbd-99d2-ef70cc82790e)


#### About Version 7
Version 7 of the model is currently in the ready state and is serving predictions. This model incorporates improvements over previous versions and includes comprehensive logging of input and output schemas as well as detailed artifact storage.

![1__#$!@%!#__Pasted Graphic 7](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/f7ad28c3-0627-4c63-85de-8c9a9bfa698a)

![2](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/f82bbc6c-c635-4623-9ba4-0eca2e210925)


#### Previous Versions
Version 6, which was active before Version 7, is also documented to provide insights into the model's evolution and basis for improvements.

![1__#$!@%!#__Pasted Graphic 3](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/85e47c6c-bb12-4cfe-8e55-73221d709547)

![3](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/4a92ac48-196b-48a2-8522-a9a18578f04f)


Version 6 has the following experimental details as shown:

![1__#$!@%!#__Pasted Graphic 2](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/75a2f24c-e0a0-4f76-b59e-e1efd07f0018)

![4](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/8b6c64a0-8d23-4a2d-8427-2aa51feea8b0)



### MLFlow Model Serving Example

Here's how you can load and serve predictions using the MLFlow models:

```python
import mlflow
from pyspark.sql.functions import struct, col

# Load the model as a Spark UDF from the MLFlow run.
logged_model = 'runs:/4f3e6879586b452d9ed31298ccd4f102/chain'
loaded_model = mlflow.pyfunc.spark_udf(spark, model_uri=logged_model)

# Predict on a Spark DataFrame.
df = df.withColumn('predictions', loaded_model(struct(*map(col, df.columns))))

## Alternatively, for predictions in a non-Spark environment:

import mlflow
import pandas as pd

# Load the model as a PyFuncModel.
logged_model = 'runs:/4f3e6879586b452d9ed31298ccd4f102/chain'
loaded_model = mlflow.pyfunc.load_model(logged_model)

# Example DataFrame for predictions.
data = {'feature1': [value1], 'feature2': [value2]}
test_data = pd.DataFrame(data)

# Generate predictions.
predictions = loaded_model.predict(test_data)
```

### Artifacts and MLmodel File

The artifacts stored in MLFlow provide a detailed breakdown of the model components. The MLmodel file is a key artifact that outlines the model configuration, dependencies, and the environment setup required to run the model. 

Artifacts details are shown below:

![1__#$!@%!#__Pasted Graphic 4](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/097ee0d5-7561-4530-9a89-092b5117969c)

![5](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/d7dd507e-7f30-48ed-9bbe-8f80125627b1)


The example snippet from the MLmodel file:

```yaml

artifact_path: chain
databricks_runtime: 12.2.x-cpu-ml-scala2.12
flavors:
  langchain:
    langchain_version: 0.1.5
    model_data: model
    model_load: runnable_load
    model_type: RunnableSequence
  python_function:
    env:
      conda: conda.yaml
      virtualenv: python_env.yaml
    loader_module: mlflow.langchain
    model_data: model
    model_load: runnable_load
    python_version: 3.9.5
mlflow_version: 2.10.1
model_size_bytes: 19481
model_uuid: c997795cb0e34606a411055e061b341c
run_id: 4f3e6879586b452d9ed31298ccd4f102
signature:
  inputs: '[{"type": "array", "items": {"type": "object", "properties": {"content":
    {"type": "string", "required": true}, "role": {"type": "string", "required": true}}},
    "name": "messages", "required": true}]'
  outputs: '[{"type": "string", "required": true}]'
utc_time_created: '2024-04-19 05:12:22.800387'

```
This configuration outlines the structure, environment, and dependencies required to operate the model within our MLOps infrastructure, ensuring efficient model testing and deployment cycles.

Overall details of Model Schema, MLFlow Model is shown:

![1__#$!@%!#__Pasted Graphic 5](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/eb9c2a72-6ba8-4afc-ab95-c77594760ee1)

![6](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/af455923-86e1-4d8c-99e5-f65e91a04103)



## Prod Environment Overview

In the production environment, model versioning and management follow a streamlined process tailored for operational stability and performance. This section outlines how models are handled in production within our MLOps setup using MLFlow.

### Models in Production

Once the production models are fully operational, they serve the advanced functionalities of a chatbot, which is a significant component of our service offerings. The models in production are managed with distinct versioning practices to ensure stability and traceability.

#### Model Registry and Versioning

Model versioning in production is handled through the MLFlow model registry, where each model version is meticulously documented and stored. Below are the details of a typical model setup in production:

![2__#$!@%!#__Pasted Graphic 5](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/3101987f-6908-4f4e-841f-1b8668845e9e)

![7](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/db552772-8fcf-4798-89cc-22093c2d4d05)


![2__#$!@%!#__Pasted Graphic 6](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/fd83786e-8670-4091-91a9-2b7ea1ff1d8f)

![8](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/81ec3fd8-4ee2-4586-860e-ccd0f6b357f2)


![2__#$!@%!#__Pasted Graphic 7](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/958886b1-3a2e-438c-9d4d-3c1673b12707)

![9](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/f441c600-592d-4cf0-816f-760b2aa33cef)



- **Model Name**: `dbdemos_advanced_chatbot_model`
- **Version**: Version 1 is currently deployed and serving.
- **Status**: Ready
- **Signature**:
  - **Inputs**: Array of messages
  - **Outputs**: Processed responses

#### Training and Artifacts

Each model version in production is linked to a specific training run, allowing us to trace back to the experimental setups and configurations. This traceability ensures that any deployed model can be audited and validated against its training parameters and outcomes.

- **Training Run**: `dbdemos_chatbot_rag`
- **Artifact Path**: `dbfs:/databricks/mlflow-tracking/2982109369405491/f528c9ed83f546fab22c57f4bdd00e49/artifacts/chain`

This path provides access to all relevant artifacts associated with the model, including the MLmodel configuration files, environmental dependencies, and the actual model data.

### Accessing and Managing Models

To access and manage the deployed models in production:

1. Navigate to the MLFlow model registry via the Databricks workspace.
2. Select the `dbdemos_advanced_chatbot_model` to view all versions and their details.
3. Each model version can be examined for its input and output signatures, artifacts, and the exact time of creation and last modification.

#### Example of Model Use in Production

Using the deployed model in production involves loading the model through MLFlow and applying it to incoming data streams for real-time predictions.

```python
import mlflow
import pandas as pd

# Load the production model as a PyFuncModel.
logged_model = 'runs:/f528c9ed83f546fab22c57f4bdd00e49/chain'
loaded_model = mlflow.pyfunc.load_model(logged_model)

# Example DataFrame for real-time predictions.
data = {'messages': ['Hello, how can I assist you today?']}
prod_data = pd.DataFrame(data)

# Generate predictions.
prod_predictions = loaded_model.predict(prod_data)

```

## Model Version Rollback

It is possible to revert to a previous version of a model in the production environment using MLFlow. For detailed steps on how to perform a model rollback, please refer to our [Model Version Rollback Guide](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/README/README_MODEL_VERSION_ROLLBACK.md).
