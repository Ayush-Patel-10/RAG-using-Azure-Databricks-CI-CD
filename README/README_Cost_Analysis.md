## Cost Analysis

The image below shows a $199.96 expense for Azure Databricks, including serverless data analytics, SQL processing, and job computation, priced by resource usage intensity. These costs reflect the scalable consumption of Azure's cloud computing services for project development.

![image 1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/2561ecd9-a1cc-414f-8dc9-54657d3b9b29)

### Large Cost on Service:

![image 2](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/d2831dc8-493b-40c4-ab6c-a62a5c1aec3f)

The provided image shows a $199.96 expense for Azure Databricks, including serverless data analytics, SQL processing, and job computation, priced by resource usage intensity. These costs reflect the scalable consumption of Azure's cloud computing services for project development

![image 3](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/b7d45e1d-a34f-439a-8c52-cc753a9f8127)

The image shows a summary of Azure Databricks Regional costs amounting to $178.01 in the US East region. This includes $94.91 for serverless real-time inferencing, $75.12 for serverless SQL operations, and $7.98 for serverless job compute, illustrating the investment in scalable analytics and processing capabilities within Azure's managed analytics service.

![image 4](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/455ab79b-7613-4272-b4ad-94ade2ff9c54)

The image indicates a charge of $21.95 for the use of Azure Databricks' premium all-purpose compute DBUs in the US East region, reflecting the cost associated with versatile compute resources provisioned for data analytics and processing tasks on the Azure cloud platform.

![image 5](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/4a329180-4091-4337-a2b2-00992d295628)

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

![image 6](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/07ff924a-6d3a-4ae7-b50d-73fc966eefb6)

![image 7](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/f6812752-21b6-4d62-9420-3ba341397b61)

![image 8](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/127258950/4ca91060-6fca-44ec-ae7b-a701aae506b3)

The image details a total Azure storage cost of $2.57, averaging $0.16 per day, distributed across various storage services. This includes Standard HDD Managed Disks at $1.93, Data Lake Storage Gen2 Namespace at $0.53, and other smaller costs for bandwidth, block blob storage, and table and queue services, indicating a diverse use of Azure's data storage solutions.
