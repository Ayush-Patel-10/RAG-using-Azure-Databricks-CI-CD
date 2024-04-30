# Project Setup on Azure & Databricks Guide

This guide provides step-by-step instructions on setting up your Azure environment to host and manage a Databricks workspace, including creating an Azure account, resource group, and Databricks workspace. Additionally, it covers the creation of an Azure Data Lake Storage Gen2 account, setting up a pipeline using Azure Data Factory, and configuring the Databricks CLI.

## Step 1: Azure Account Creation

Before utilizing Azure services, including Azure Databricks, an Azure account is required. If you don't have one, follow these steps to create one:

1. **Go to the Azure Sign-up Page**: Navigate to the [Azure Portal sign-up page](https://azure.com).
2. **Start the Sign-up Process**: Click on the "Start free" button to begin the account creation process.
3. **Provide Your Details**: Fill in your personal information, including your name, email address, and phone number. You will also need to choose a verification method (either SMS or call) to verify your identity.
4. **Verification**: Complete the verification process using the method you selected in the previous step.
5. **Agreement and Subscription**: Read and agree to the Azure subscription agreement, offer details, and terms of use. Then, click "Sign up".
6. **Wait for Account Setup**: Azure will take a few moments to set up your account. Once complete, you can access the Azure Portal.

## Step 2: Resource Group Creation inside Azure Account

A resource group is a container that holds related resources for an Azure solution. To create one:

1. **Log into Azure Portal**: After setting up your Azure account, log in to the [Azure Portal](https://portal.azure.com).
2. **Navigate to Resource Groups**: Find and select "Resource groups" from the navigation pane or use the search bar.
3. **Create a Resource Group**: Click on "Add" or "Create resource group".
4. **Specify Resource Group Details**: Enter a name, select your subscription, and choose the region for your resources.
5. **Review and Create**: Review your settings and click "Create".

## Step 3: Creation of Storage Account (ADLS Gen2) inside the Resource Group

To create an ADLS Gen2:

1. **Create a Storage Account**: Select "Create a resource", search for "Storage account", and click "Create".
2. **Specify Storage Account Details**: In the "Basics" tab, select your subscription and resource group. Enter a name and choose the same region as your resource group.
3. **Select Account Type**: In the "Advanced" tab, enable "Hierarchical namespace".
4. **Review and Create**: Adjust the remaining settings as necessary, then click "Review + Create" and "Create".
5. **Access and Configure the Storage Account**: Navigate to your storage account from the Azure Portal to manage settings.
<img width="1075" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/94106490-f79c-4298-9c14-ac7bcfd5ca2e">

## Step 4: Databricks Workspace Creation inside Resource Group

With a resource group ready, proceed to create a Databricks workspace:

1. **Open the Azure Marketplace**: Go to "Create a resource" from the dashboard.
2. **Search for Databricks**: Type "Databricks" and select "Azure Databricks".
3. **Create a Databricks Workspace**: Click "Create" and provide the necessary information, including name, subscription, resource group, location, and pricing tier.
4. **Review and Create**: After filling out the details, click "Create".
5. **Access Your Databricks Workspace**: Navigate to "All resources", find your Databricks workspace, and click to open it.
<img width="1091" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/c0eb274e-32f9-4ad6-90b3-2cf02fffef0c">

### 4.1. Meta Store Creation Inside Databricks

The Unity Catalog Metastore in Azure Databricks serves as a centralized repository for storing and managing metadata for various data objects. The following steps outline how to create and configure a Metastore with Azure Data Lake Storage Gen2 (ADLS Gen2) as the underlying storage.

#### Step 4.1.1: Configure Storage for Metastore

**Create a storage Account ADLS Gen2** which will hold the metadata for Unity Catalog Metastore and the objects.

#### Step 4.1.2: Create and Configure Metastore

1. **Create a Storage Account**:
    - Navigate to the Azure portal and create a new storage account.
    - Ensure to enable the hierarchical namespace, which is a requirement for ADLS Gen2.

2. **Create a Storage Container**:
    - Within the Storage Account, create a new container to store the Unity Catalog Metastore's metadata and managed data.

3. **Set Up Databricks Access to Storage**:
    - Create an "Access Connector for Azure Databricks" as a resource in the Azure portal, which serves as a managed identity for Databricks to access the storage container.
    - Assign the role of 'Storage Blob Data Contributor' to the access connector using the IAM policy of the storage account.

#### Step 4.1.3: Create Metastore through Databricks UI

1. **Create an Azure Databricks Workspace**:
    - While creating the workspace, choose a premium tier for role-based access controls.

2. **Log in to the Workspace**:
    - Access the Azure Databricks workspace using your credentials.

3. **Navigate and Create Metastore**:
    - Go to the data icon on the left panel and click on 'Create Metastore'.
    - Provide a name for the metastore, select the region, and enter the path for the ADLS Gen2 container created in the earlier steps.
    - Input the access container ID.
    - Click 'Create' to finalize the metastore creation.

4. **Link Metastore to Workspaces**:
    - Assign the metastore to the required Databricks workspace by selecting the workspace, clicking 'Assign', and then 'Enable' to establish the linkage.

By completing these steps, you'll have a fully configured Metastore that is ready for use with multiple Databricks workspaces, allowing for a more centralized and efficient management of data assets.

### Step 4.2: Creating the cluster
1. Once metastore is created then navigate to compute. Click on the create compute on top right.
2. Choose the required configurations and click on create compute.
3. After creating click on view json to get cluster id
<img width="807" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/a5e302c3-e7c8-4511-aba1-86e0160b98a6">

### Step 4.3: Creation of catalogs and schema and assigning permissions
1. **Navigate to Catalog**: Click on the Catalog icon.
2. **Select Catalog**: In the Catalog pane on the left, select the catalog where you wish to create the schema.
3. **Create Schema**:
    - Click `Create schema` in the detail pane.
    - Enter a name for the schema and, optionally, a comment to describe its purpose.
    - (Optional) Specify a managed storage location if required, which also necessitates `CREATE MANAGED STORAGE` privilege on the target external location.
4. **Set Permissions**:
    - Assign appropriate permissions for the schema, referencing Unity Catalog privileges and securable objects guidelines.
<img width="721" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/8e8f1042-1626-4a6a-8735-9be7135d7881">

### Step 4.4: Creating access tokens in Databricks
1. **Access User Settings**: Open the Databricks workspace, go to the sidebar, click on your profile or user icon, and select 'User Settings'.
2. **Generate Token**: Navigate to the 'Access Tokens' tab and click on 'Generate New Token'.
3. **Save Token**: Enter a description, set the expiration time, click 'Generate', and then securely save the token that is displayed, as you won’t be able to see it again.
<img width="941" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/1a72d719-88b5-4d3a-a7e4-5c1b3c38e6b5">


### Using SQL Commands

Alternatively, schemas can be created using SQL commands in a Databricks notebook:

```sql
CREATE SCHEMA IF NOT EXISTS schema_name COMMENT 'Description of schema purpose';
```

### Step 4.5: Installing libraries on Cluster

We are manually installing all the required libraries while creating the cluster. Since, we can’t create a conda environment. As it is not supported on [Azure](https://learn.microsoft.com/en-us/azure/databricks/archive/legacy/conda).

<img width="906" alt="image" src="https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/be70052c-15bd-43ae-a68c-2f5a0b308a79">

# Project Setup on Github Guide

We need to setup the following secrets and access tokens in our github repo on which this code sits. These will help the github workflows to interact with Azure & databricks account to setup the CI-CD pipeline

1. **`DATABRICKS_TOKEN`**: 
   - A personal access token for authenticating with Databricks services.
   - **How to Obtain**: Generated within the Databricks workspace under user settings.

2. **`EMAIL_PASSWORD`**:
   - The password for an email account used by the system to send notifications or alerts.
   - **How to Obtain**: Set up through the email provider's account settings.

3. **`EMAIL_USERNAME`**:
   - The username for the aforementioned email account.
   - **How to Obtain**: Typically the full email address, set up with the email service provider.

4. **`PROD_AZURE_SP_APPLICATION_ID`**:
   - The application (client) ID for the Azure Service Principal in the production environment.
   - **How to Obtain**: Created in Azure Active Directory → App registrations.

5. **`PROD_AZURE_SP_CLIENT_SECRET`**:
   - A secret key associated with the Azure Service Principal for production.
   - **How to Obtain**: Created in Azure Active Directory → App registrations → Certificates & secrets.

6. **`PROD_AZURE_SP_TENANT_ID`**:
   - The tenant ID for the Azure Active Directory where the Service Principal is registered for production.
   - **How to Obtain**: Found in Azure Active Directory → Properties.

7. **`STAGING_AZURE_SP_APPLICATION_ID`**:
   - Similar to `PROD_AZURE_SP_APPLICATION_ID` but for the staging environment.
   - **How to Obtain**: Follow the same steps as the production keys but within the staging environment.

8. **`STAGING_AZURE_SP_CLIENT_SECRET`**:
   - Corresponds to `PROD_AZURE_SP_CLIENT_SECRET` for the staging environment.
   - **How to Obtain**: Generated similarly to the production environment's client secret.

9. **`STAGING_AZURE_SP_TENANT_ID`**:
   - Tenant ID equivalent to `PROD_AZURE_SP_TENANT_ID` for the staging environment.
   - **How to Obtain**: Acquired from the Azure portal under the Azure Active Directory section for staging.

10. **`WORKFLOW_TOKEN`**:
    - A fine-grained personal access token used within GitHub to authenticate and trigger workflow actions.
    - **How to Obtain**: Go to GitHub settings, navigate to Developer settings → Personal access tokens → Fine-grained tokens. Create a new token with the appropriate scopes required for your workflows.

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/156069267/8409d0a6-7ea1-4c8c-a32d-202f2879c99a)

# Project setup on loacl system Guide  

## Step 1: Installing Databricks CLI 

### For Windows using WSL: Installing Databricks CLI on VSCode 

1. **Check if `curl` is installed**: Run the following command in your WSL terminal:
    ```bash
    curl -V
    ```

2. **Install `curl` if necessary**: If `curl` is not installed, use the package manager for your Linux distribution to install it.

3. **Download and install the Databricks CLI**: Execute the following command in your WSL terminal:
    ```bash
    curl -fsSL https://raw.githubusercontent.com/databricks/setup-cli/main/install.sh | sudo sh
    ```

    This command downloads the installation script from the Databricks CLI repository on GitHub and executes it with root privileges using `sudo`.

4. **Verify installation**: After the installation is complete, verify that the Databricks CLI is installed correctly by running:

### For Macos: Installing Databricks CLI on vscode 

Follow the steps on the [Databricks CLI installation guide](https://docs.databricks.com/en/dev-tools/cli/install.html).

    brew tap databricks/tap
    brew install databricks

```bash
brew -v
# Or:
databricks version
```

If the installation was successful, you should see the version number of the Databricks CLI printed in the terminal.

##  Step 2: Configure azure-cli login
Use the command az login on the terminal of the current directory.

```bash
az login
```
