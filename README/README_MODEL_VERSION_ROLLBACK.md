## Model Version Controlling:

To revert to a prior version of a model in a production environment, you can follow the procedure outlined below:

### Step 1: Navigate to the Serving Section
Access the "Serving" section via the left sidebar in Databricks, which displays a list of all active serving endpoints.

 ![1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/9831070d-0135-4784-a40a-f96092191a04)


### Step 2: Select the Deployed Model
Identify and select the model currently deployed in production. This will present you with a screen similar to the following:

![2](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/17973f2f-d082-4d3f-a934-5e0851b3dc25)


### Step 3: Edit Endpoint
In the upper-right corner, click on "Edit endpoint". Within this area, locate the "Served entities" section, which includes a version dropdown menu. This menu allows you to view and select from previously deployed model versions. Choose the desired version and confirm the rollback by clicking "Update".

<img width="773" alt="3" src="https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/5ed40b13-21bb-4254-8768-9364d59cb2eb">

