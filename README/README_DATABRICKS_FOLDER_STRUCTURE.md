## Production Environment Structure for LLMOps

This document outlines the folder structure and CI/CD flow of the Databricks workspace for the `LLMOps` project.

## Directory Overview

Within the `.bundle` directory, the production environment is structured into several main components:

- `test`: Holds the latest development files and code. It is the initial stage for all changes.
- `staging`: Contains files and artifacts that passed unit and integration tests from the `test` environment.
- `prod`: Contains the production-ready files that have passed all stages of testing and review.

![1](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/f12b7125-79f9-480f-b8d8-18426b0557c6)


## CI/CD Flow

1. Developers push changes to the `test` folder.
2. If unit and integration tests pass, changes are automatically deployed to the `staging` folder.
3. Upon approval and merge of a pull request from `main` to `release`, the changes are deployed to the `prod` folder for production use.

## Detailed Folder Structure
Below is the repository structure outlining the key directories and files within the `.bundle` directory.

```plaintext
.bundle/
│
├── LLMOps/                                                 # GitHub project root folder
│ ├── test/                                                 # Testing environment with latest development files
│ ├── staging/                                              # Staging environment with tested artifacts ready for production
│ └── prod/                                                 # Production environment with live, production-ready files
│     ├── artifacts/                                        # Contains artifacts for deployment
│     ├── files/                                            # Active files used in the production environment
│     │   ├── DataStreaming/                                # Contains scripts and configurations for data streaming
│     │   ├── deployment/                                   # Deployment configurations and scripts
│     │   ├── monitoring/                                   # Monitoring and logging scripts
│     │   ├── rag_code_files/                               # Regulatory and governance code files
│     │   ├── resources/                                    # Necessary resources like configuration files
│     │   ├── tests/                                        # Integration and acceptance test suites
│     │   ├── training/                                     # Training scripts and notebooks for models
│     │   ├── validation/                                   # Validation scripts for data quality checks
│     │   ├── __init__.py                                   # Initialization script for Python packages
│     │   ├── databricks.yml                                # Configuration file for Databricks environments
│     │   ├── project_params.json                           # Project parameters in a JSON file
│     │   ├── pytest.ini                                    # Configuration for the pytest framework
│     │   ├── README.md                                     # Documentation for the production setup
│     │   └── requirements.txt                              # Python package dependencies
│     └── state/                                            # Holds state information for infrastructure provisioning
│         ├── metadata.json                                 # Metadata related to the state management
│         └── terraform.tfstate                             # Terraform's state file for infrastructure
```
![2](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/e88d4f9c-f5e0-4cc5-bbbd-88e4da3a70e7)

![3](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/950b0cd5-db11-4f28-b503-38c2bb443f25)

![4](https://github.com/Ayush-Patel-10/RAG-using-Azure-Databricks-CI-CD/assets/78248225/dc01b5c8-773c-4fc0-9349-7bd424a8e785)


## Notes

- The `artifacts` folder contains generated artifacts such as binary files or libraries needed for deployment.
- The `files` folder includes scripts, configuration files, and other necessary resources for the production environment to function correctly.
- The `state` folder contains state information, particularly for infrastructure managed by Terraform, which ensures idempotency and correct infrastructure setup.

## Additional Information

- The `README.md` file within the `files` folder provides documentation specific to the production setup.
- `terraform.tfstate` in the `state` folder tracks the state of the infrastructure and is crucial for Terraform operations.
