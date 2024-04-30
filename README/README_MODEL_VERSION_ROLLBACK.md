## Model Version Controlling:

To revert to a prior version of a model in a production environment, you can follow the procedure outlined below:

### Step 1: Navigate to the Serving Section
Access the "Serving" section via the left sidebar in Databricks, which displays a list of all active serving endpoints.

 ![MicrosoftTeams-image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/92932565-ba21-4521-b50f-62996a31be23)

### Step 2: Select the Deployed Model
Identify and select the model currently deployed in production. This will present you with a screen similar to the following:

![MicrosoftTeams-image (1)](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/b7ab0767-73f8-4f26-8e83-e13337a21414)

### Step 3: Edit Endpoint
In the upper-right corner, click on "Edit endpoint". Within this area, locate the "Served entities" section, which includes a version dropdown menu. This menu allows you to view and select from previously deployed model versions. Choose the desired version and confirm the rollback by clicking "Update".

<img width="773" alt="MicrosoftTeams-image (2)" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/fae6d74b-dbeb-421d-bd0a-ab1a10cc141a">
