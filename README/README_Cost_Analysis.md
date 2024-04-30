## Cost Analysis

The image below shows a $199.96 expense for Azure Databricks, including serverless data analytics, SQL processing, and job computation, priced by resource usage intensity. These costs reflect the scalable consumption of Azure's cloud computing services for project development.

<p align="center">
  <img src="https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/1e1de446-4571-452e-8517-93ca3c300596" alt="Azure Databricks Expense">
</p>
### Large Cost on Service:

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/30ce92fe-e35d-42c8-818c-ba2ea9bce9e7)

The provided image shows a $199.96 expense for Azure Databricks, including serverless data analytics, SQL processing, and job computation, priced by resource usage intensity. These costs reflect the scalable consumption of Azure's cloud computing services for project development

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/03faccd2-baf9-4534-87c8-fe7242bf62f1)

The image shows a summary of Azure Databricks Regional costs amounting to $178.01 in the US East region. This includes $94.91 for serverless real-time inferencing, $75.12 for serverless SQL operations, and $7.98 for serverless job compute, illustrating the investment in scalable analytics and processing capabilities within Azure's managed analytics service.

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/2e71fbd8-e15e-4b81-a921-a748bc5edb5c)

The image indicates a charge of $21.95 for the use of Azure Databricks' premium all-purpose compute DBUs in the US East region, reflecting the cost associated with versatile compute resources provisioned for data analytics and processing tasks on the Azure cloud platform.

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/451dc203-2564-4908-a23f-c2eae4d96269)

The image shows a charge of $16.90 for the usage of Azure's Dv2 Series Virtual Machines, specifically a D3 v2 instance in the East US region, under the compute category. This cost reflects the usage-based pricing for scalable virtual computing resources on Azure.

### Cost Breakdown:

- **Serverless Realtime Inference DBU:** $94.91 used, possibly for real-time text extraction and processing from PDFs and docx files.
- **All-purpose Compute DBU:** $21.95, likely for running the Python script and document-related computations, deploying machine learning models using MLFlow and managing endpoints, configuring the serving endpoints and possibly for running validation tasks on the deployed models, for tasks that monitor data quality and run analysis, which may involve loading data and running checks using the installed libraries.
-   **Virtual Machines D3 v2:** $16.90, for the underlying compute infrastructure.
-   **Serverless SQL DBU:** $75.12, possibly for operations such as data retrieval and vector search queries within the vector database, SQL operations for model metadata retrieval.
-   **Overall Cluster Costs:** The cluster’s configuration as a single-node, single-user cluster with auto-termination after 120 minutes of inactivity suggests a cost-optimization strategy. The cost per notebook is not directly available but would be a portion of the total cost, $199.96, proportional to the compute time and resources each notebook used.

Each notebook’s costs are influenced by the type of tasks it performs, with document processing, SQL operations, machine learning deployment, model management, and data monitoring each consuming resources differently. The total cost is an aggregate, with individual notebooks contributing to this total based on their resource usage.

### Negligible or no costs on Service:

Majorly consists of Storage costs.

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/a81af2e1-0cd4-4e0d-b7f7-e4c7896b93ec)

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/250c34db-4a49-4558-b3ed-4a8bb3363c1b)

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/78248225/561723bb-a033-4955-aa85-d4537fe1bb51)

The image details a total Azure storage cost of $2.57, averaging $0.16 per day, distributed across various storage services. This includes Standard HDD Managed Disks at $1.93, Data Lake Storage Gen2 Namespace at $0.53, and other smaller costs for bandwidth, block blob storage, and table and queue services, indicating a diverse use of Azure's data storage solutions.
