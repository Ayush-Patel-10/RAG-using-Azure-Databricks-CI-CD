What all tables are there.. 
Test Environment.. 
8 tables, 1 volumes, 1 model

Tables are similar to prod environment.. 
Prod Environment.. 
8 tables, 1 volumes, 1 model


There are 8 tables for prod, with the lineages. 
The 8 Tables are shown below:
![Blank diagram (3)](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/9d060738-3eb9-45d9-91ab-b50f5c0a3693)



## Lineage Graphs between the Tables are shown as below:

![Blank diagram (1)](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/d42137fd-d138-4e2f-8568-2bdc3d99dd7c)

![Blank diagram (2)](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/2af050f1-0517-4b36-8ba7-9b6d7420578d)

## Table 1: `prod.my_mlops_project_luv_v6.databricks_pdf_documentation`

### Overview
The `databricks_pdf_documentation` table is a managed table designed to hold metadata about various PDF documents that are part of the project's resources. It facilitates the full-text search capability, allowing for quick retrieval of documentation content based on user queries. The metadata includes unique identifiers, the document's URL, the extracted text content, and the document's content embeddings.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/prod/__unitystorage/schemas/d6d20002-cd15-4da7-9234-b83abffc2529/tables/8f41e694-e5f6-4b06-abe3-a046fe4cc388`
- **Properties**:
  - `delta.lastCommitTimestamp=1713564108000`
  - `delta.lastUpdateVersion=2`
  - `delta.minWriterVersion=6`
  - `delta.enableChangeDataFeed=true`
  - `delta.minReaderVersion=1`
- **Generation**: 2
- **Created At**: 4/19/2024, 2:24:44 AM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: 8f41e694-e5f6-4b06-abe3-a046fe4cc388

### Schema
The table consists of the following columns:

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `id` | `BIGINT` | A unique identifier assigned to each document. |
| `url` | `STRING` | The location URL where the document can be accessed. |
| `content` | `STRING` | The full extracted textual content from the document. |
| `embedding` | `ARRAY<FLOAT>` | A vector representation of the document content, used for similarity search and retrieval. |

### Sample Data
A glimpse into the data the table holds (Note: real values not disclosed for brevity):

| `url` | `content` | `embedding` |
|-------|-----------|-------------|
| URL to document | Extracted text from the document | Content embedding vector |

### Lineage
The data in this table is populated from the following sources:

- **Upstream Source**: `pdf_raw` table which contains the raw PDF files.
- **Transformation Notebook**: An untitled notebook from April 18, 2024, is used for the data extraction and transformation pipeline.
- **Related Code**: `prod_code_Bharath`, which may contain related processing scripts or workflows.

### Usage Example
The table can be used to search for specific content within the documents. An example SQL query to retrieve documents containing a particular keyword would be:

```sql
SELECT url, content
FROM `prod.my_mlops_project_luv_v6.databricks_pdf_documentation`
WHERE content LIKE '%desired_keyword%';
```

## Table 2: `prod.my_mlops_project_luv_v6.pdf_raw`

### Overview
The `pdf_raw` table is a managed storage location for raw PDF files within the project. It contains the initial metadata about the documents before they are processed. This table is vital for the upstream data pipeline, serving as the first point of entry for PDF documents in the system.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/prod/__unitystorage/schemas/2f3c9e94-71a4-4f99-9775-21810600a521/tables/59c69acc-d2bc-43a1-a528-0b42bddbf2e2`
- **Properties**:
  - `delta.lastCommitTimestamp=1713505579000`
  - `delta.lastUpdateVersion=9`
  - `delta.minReaderVersion=1`
  - `delta.minWriterVersion=2`
- **Generation**: 9
- **Created At**: 4/18/2024, 10:54:09 PM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: 59c69acc-d2bc-43a1-a528-0b42bddbf2e2

### Schema
The table consists of the following columns:

| Column Name       | Data Type   | Description |
|-------------------|-------------|-------------|
| `path`            | `STRING`    | The file path of the PDF document within the data store. |
| `modificationTime`| `TIMESTAMP` | The timestamp of the last modification made to the PDF document. |
| `length`          | `BIGINT`    | The size of the PDF document in bytes. |
| `content`         | `BINARY`    | The binary content of the PDF document. |

### Sample Data
A sample of the data contained in the table is as follows (Note: actual binary content is truncated):

| `path` | `modificationTime` | `length` | `content` |
|--------|---------------------|----------|-----------|
| dbfs:/mnt/datafromazure/Prod_Files/Data-AI-in-Fed-Gov-Ebook.pdf | 2024-04-16T22:17:16.000+00:00 | 5002642 | JVBERi0xL... (truncated) |
| dbfs:/mnt/datafromazure/Prod_Files/030521-2-The-Delta-Lake-Series-Complete-Collection.pdf | 2024-04-16T22:17:15.000+00:00 | 4876146 | JVBERi0xL... (truncated) |

### Lineage
This table receives data from the following processes:
- **Workflows**: `prod-my_mlops_project_luv_v6-model-training-job` for model training and data processing.
- **Notebooks**:
  - `01`: Initial data processing notebook.

### Usage
The table serves as the foundation for document processing pipelines. It is not directly queried for content retrieval but is used in data transformation jobs. An example transformation might involve extracting text from the `content` column to feed into a text analysis pipeline.

## Table 3: `test.my_mlops_project_luv_v6.dbdemos_endpoint_advanced1_test_my_mlops_project_luv_v6_payload`

### Overview
The `dbdemos_endpoint_advanced1_test_my_mlops_project_luv_v6_payload` table is designed to capture the payload data pertaining to the requests and responses handled by the advanced1 endpoint within the MLOps project. This includes detailed logging of client and Databricks request IDs, timestamps, request and response content, as well as execution metrics.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/test/__unitystorage/schemas/2f3c9e94-71a4-4f99-9775-21810600a521/tables/a2e176d1-c6ed-4fa1-add6-974a88ffd3f6`
- **Properties**:
  - `delta.lastCommitTimestamp=1713499476698`
  - `delta.lastUpdateVersion=4`
- **Generation**: Not specified
- **Created At**: 4/18/2024, 9:20:45 PM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: a2e176d1-c6ed-4fa1-add6-974a88ffd3f6

### Schema
The table consists of the following columns:

| Column Name        | Data Type | Description |
|--------------------|-----------|-------------|
| `client_request_id`| `STRING`  | Unique identifier for the client request. |
| `databricks_request_id` | `STRING` | Unique identifier for the request as logged by Databricks. |
| `date`             | `DATE`    | The date when the request was made. |
| `timestamp_ms`     | `BIGINT`  | The exact timestamp of the request in milliseconds. |
| `status_code`      | `INT`     | The HTTP status code returned by the endpoint. |
| `execution_time_ms`| `BIGINT`  | The time taken to execute the request, in milliseconds. |
| `request`          | `STRING`  | The actual request content in string format. |
| `response`         | `STRING`  | The response content returned by the endpoint. |
| `sampling_fraction`| `DOUBLE`  | The fraction of requests sampled for logging, if applicable. |
| `request_metadata` | `MAP`     | Additional metadata about the request, if any. |

### Sample Data
Due to the large size of request and response content, a detailed display of sample data is not provided here. Generally, the data includes JSON-formatted text strings containing conversational exchanges, their resultant model outputs, and associated metadata.

### Lineage
Data for this table is influenced by the following notebooks:
- `05-Inference-Tables-Analysis-Notebook-with-LLM-Metrics` (Downstream)
- `04_Deploy_model_as_endpoint` (Downstream)

These notebooks are integral to the data transformation and analysis processes that provide insights into the model's performance and interactions.

### Usage
This table is primarily used for monitoring, debugging, and analyzing the performance of the `advanced1` endpoint. It is not directly queried for operational purposes but is utilized in analysis workflows for understanding endpoint behavior and user interactions. Example analysis might include:

```sql
SELECT 
    date, 
    AVG(execution_time_ms) AS avg_execution_time 
FROM 
    `test.my_mlops_project_luv_v6.dbdemos_endpoint_advanced1_test_my_mlops_project_luv_v6_payload` 
GROUP BY 
    date;
```

## Table 4: `test.my_mlops_project_luv_v6.dbdemos_endpoint_advanced1_test_my_mlops_project_luv_v6_processed`

### Overview
The `dbdemos_endpoint_advanced1_test_my_mlops_project_luv_v6_processed` table contains processed data from the advanced1 endpoint of the MLOps project. This table captures metrics and detailed data from model interactions, including inputs, outputs, and various calculated metrics such as toxicity, perplexity, token count, and readability indexes of the conversational content.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/test/__unitystorage/schemas/2f3c9e94-71a4-4f99-9775-21810600a521/tables/5649e6b4-3734-4912-a71b-98f173893581`
- **Properties**:
  - `delta.lastCommitTimestamp=1713506714000`
  - `delta.lastUpdateVersion=4`
  - `delta.minWriterVersion=5`
  - `delta.enableChangeDataFeed=true`
  - `delta.minReaderVersion=2`
  - `delta.columnMapping.mode=name`
  - `delta.columnMapping.maxColumnId=16`
- **Generation**: 4
- **Created At**: 4/18/2024, 9:49:40 PM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: 5649e6b4-3734-4912-a71b-98f173893581

### Schema
The table is structured with the following columns:

| Column Name                        | Data Type | Description |
|------------------------------------|-----------|-------------|
| `__db_date`                        | `DATE`    | The date on which the log was recorded. |
| `execution_time_ms`                | `BIGINT`  | The time taken by the model to execute the input in milliseconds. |
| `__db_timestamp`                   | `BIGINT`  | A timestamp marking when the log was recorded. |
| `__db_model_id`                    | `STRING`  | Identifier for the specific model version used. |
| `input`                            | `STRING`  | The input text to the model. |
| `output`                           | `STRING`  | The output text from the model. |
| `toxicity(input)`                  | `DOUBLE`  | Toxicity score for the input. |
| `perplexity(input)`                | `DOUBLE`  | Perplexity score for the input. |
| `token_count(input)`               | `INT`     | Number of tokens in the input. |
| `flesch_kincaid_grade(input)`      | `DOUBLE`  | Flesch-Kincaid grade level for the input. |
| `automated_readability_index(input)`| `DOUBLE`  | Automated readability index for the input. |
| `toxicity(output)`                 | `DOUBLE`  | Toxicity score for the output. |
| `perplexity(output)`               | `DOUBLE`  | Perplexity score for the output. |
| `token_count(output)`              | `INT`     | Number of tokens in the output. |
| `flesch_kincaid_grade(output)`     | `DOUBLE`  | Flesch-Kincaid grade level for the output. |
| `automated_readability_index(output)` | `DOUBLE` | Automated readability index for the output. |

### Sample Data
The sample data is extensive and contains detailed conversational logs. Due to the size and complexity, only the structure of the data is described here.

### Lineage
The following notebooks are part of the data lineage:
- `05-Inference-Tables-Analysis-Notebook-with-LLM-Metrics` which performs downstream analysis on the model's outputs.
- `04_Deploy_model_as_endpoint` which is used for deploying the model as an endpoint.

These notebooks are essential for processing and analyzing the data contained within this table.

### Usage
The table is utilized for in-depth analysis of model performance and interaction quality. Metrics gathered here inform improvements and iterations on the model. An example use case could be analyzing the average toxicity of inputs and outputs over time to ensure conversational quality remains within acceptable boundaries.

## Table 5: `prod.my_mlops_project_luv_v6_processed_drift_metrics`

### Overview
This table is a managed dataset within the production environment that records and tracks metrics related to concept drift in model performance over time. It is used to monitor changes in data distribution or model behavior that may impact the effectiveness of predictive models.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/prod/__unitystorage/schemas/2f3c9e94-71a4-4f99-9775-21810600a521/tables/05a4d97b-bf91-4ca7-9477-0941b56ba864`
- **Properties**:
  - `delta.lastCommitTimestamp=1713491928000`
  - `delta.lastUpdateVersion=0`
  - `delta.minReaderVersion=1`
  - `delta.minWriterVersion=2`
- **Created At**: 4/18/2024, 9:58:49 PM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: 05a4d97b-bf91-4ca7-9477-0941b56ba864

### Schema
The schema is extensive and includes various metrics that capture the nature and extent of drift. For example, the `percent_null_delta` column measures the change in the proportion of null values for a particular feature, which is one of many indicators of potential drift in data.

### Lineage
The table is updated via workflows and queries that are executed based on the data processed through notebooks such as `05-Inference-Tables-Analysis-Notebook-with-LLM-Metrics`. The data is further used in various downstream dashboards to visually represent drift metrics, providing actionable insights for data scientists and engineers.

### Usage
While specific column descriptions are too numerous to list, the table is critical for understanding how models may degrade or behave differently as data evolves. By tracking metrics like `percent_null_delta`, teams can preemptively identify issues and make necessary adjustments to models. Here's an example query that could be run against this table:

```sql
SELECT column_name, percent_null_delta
FROM `prod.my_mlops_project_luv_v6_processed_drift_metrics`
WHERE percent_null_delta > 0.05;
```

This query would identify columns where there has been a significant increase in null values, suggesting a need for investigation into data quality or model robustness.

## Table 6: `prod.my_mlops_project_luv_v6.evaluation_dataset`

### Overview
The `evaluation_dataset` table contains data used for evaluating the performance of models within the project. It consists of a set of questions along with their corresponding answers, which can be used to test the accuracy and relevance of responses provided by the models.

### Details
- **Owner**: maaheshwarispandan97@outlook.com

### Schema
The table includes the following fields:

| Column Name | Data Type | Description                       |
|-------------|-----------|-----------------------------------|
| `id`        | `BIGINT`  | A unique identifier for each entry.|
| `question`  | `STRING`  | The question text posed to the model.|
| `answer`    | `STRING`  | The expected answer text for the corresponding question.|

### Usage
This table is used to run evaluations against models to measure their performance on a standardized set of queries. This process helps in ensuring that the model is producing correct and sensible answers.

An example query to retrieve a sample question-answer pair for evaluation could be:

```sql
SELECT question, answer
FROM `prod.my_mlops_project_luv_v6.evaluation_dataset`
WHERE id = 123;
```

## Table 7: `prod.my_mlops_project_luv_v6_processed_profile_metrics`

### Overview
The `prod.my_mlops_project_luv_v6_processed_profile_metrics` table contains a comprehensive set of profile metrics collected from advanced model endpoints within the production environment. It's designed to capture a range of statistical parameters to monitor the characteristics of data processed by these models.

### Details
- **Type**: MANAGED
- **Storage Location**: `abfss://pdfscontainer@adlsluvapr15.dfs.core.windows.net/prod/__unitystorage/schemas/d6d20002-cd15-4da7-9234-b83abffc2529/tables/77fd68ec-0d67-4f9f-99a6-ad421379fe43`
- **Properties**:
  - `delta.lastCommitTimestamp=1713510032000`
  - `delta.lastUpdateVersion=0`
  - `delta.minReaderVersion=1`
  - `delta.minWriterVersion=2`
- **Created At**: 4/19/2024, 3:00:34 AM
- **Created By**: maaheshwarispandan97@outlook.com
- **Table Id**: 77fd68ec-0d67-4f9f-99a6-ad421379fe43

### Schema
This table's extensive schema includes columns for various measures such as `max_length`, `avg_length`, `percent_null`, `percent_zeros`, and `percent_distinct`, amongst others, which together provide a multi-dimensional view of the data profiles.

### Lineage
The profiling data is derived from upstream processed data and drift metrics tables, and feeds into further downstream analyses:
- **Upstream**:
  - `prod.my_mlops_project_luv_v6_processed`
- **Downstream**:
  - `prod.my_mlops_project_luv_v6_processed_drift_metrics`

### Usage
The table offers the capability to closely monitor data distributions and patterns, providing critical insights for data quality and model performance management. However, not all metrics are monitored actively as they may not all contribute meaningfully to performance insights.

For example, while `percent_null` metrics offer insight into data completeness, parameters like `avg_length` might not be as crucial depending on the context of the data.

### Note
Due to the extensive nature of the metrics captured, only a subset that provides the most value is actively used in monitoring. This selective approach ensures focus on the most impactful metrics while maintaining the ability to expand the monitoring scope as needed.



