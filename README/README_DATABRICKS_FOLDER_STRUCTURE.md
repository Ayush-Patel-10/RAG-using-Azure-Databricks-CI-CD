## Production Environment Structure for my_mlops_project_luv_v6

This document outlines the folder structure and CI/CD flow of the Databricks workspace for the `my_mlops_project_luv_v6` project.

## Directory Overview

Within the `.bundle` directory, the production environment is structured into several main components:

- `test`: Holds the latest development files and code. It is the initial stage for all changes.
- `staging`: Contains files and artifacts that passed unit and integration tests from the `test` environment.
- `prod`: Contains the production-ready files that have passed all stages of testing and review.

![3__#$!@%!#__Pasted Graphic](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/0d7d3478-81f0-49d4-a844-82fa4a0b9a79)

## CI/CD Flow

1. Developers push changes to the `test` folder.
2. If unit and integration tests pass, changes are automatically deployed to the `staging` folder.
3. Upon approval and merge of a pull request from `main` to `release`, the changes are deployed to the `prod` folder for production use.

## Detailed Folder Structure
Below is the repository structure outlining the key directories and files within the `.bundle` directory.

.bundle/
```plaintext
.bundle/
│
├── my_mlops_project_luv_v6/ # GitHub project root folder
│ ├── test/ # Testing environment with latest development files
│ ├── staging/ # Staging environment with tested artifacts ready for production
│ └── prod/ # Production environment with live, production-ready files
│     ├── artifacts/ # Contains artifacts for deployment
│     ├── files/ # Active files used in the production environment
│     │   ├── DataStreaming/ # Contains scripts and configurations for data streaming
│     │   ├── deployment/ # Deployment configurations and scripts
│     │   ├── monitoring/ # Monitoring and logging scripts
│     │   ├── rag_code_files/ # Regulatory and governance code files
│     │   ├── resources/ # Necessary resources like configuration files
│     │   ├── tests/ # Integration and acceptance test suites
│     │   ├── training/ # Training scripts and notebooks for models
│     │   ├── validation/ # Validation scripts for data quality checks
│     │   ├── __init__.py # Initialization script for Python packages
│     │   ├── databricks.yml # Configuration file for Databricks environments
│     │   ├── project_params.json # Project parameters in a JSON file
│     │   ├── pytest.ini # Configuration for the pytest framework
│     │   ├── README.md # Documentation for the production setup
│     │   └── requirements.txt # Python package dependencies
│     └── state/ # Holds state information for infrastructure provisioning
│         ├── metadata.json # Metadata related to the state management
│         └── terraform.tfstate # Terraform's state file for infrastructure
```

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/6ce3d283-ca5b-428e-92cf-7189588477f0)

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/da278df7-c49e-4c31-a6ea-f88026473245)

![image](https://github.com/luv91/my_mlops_project_luv_v6/assets/10795176/af41377d-3cdc-4d20-9a6a-d9d141419ae5)


## Notes

- The `artifacts` folder contains generated artifacts such as binary files or libraries needed for deployment.
- The `files` folder includes scripts, configuration files, and other necessary resources for the production environment to function correctly.
- The `state` folder contains state information, particularly for infrastructure managed by Terraform, which ensures idempotency and correct infrastructure setup.

## Additional Information

- The `README.md` file within the `files` folder provides documentation specific to the production setup.
- `terraform.tfstate` in the `state` folder tracks the state of the infrastructure and is crucial for Terraform operations.
