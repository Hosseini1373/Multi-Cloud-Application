# Multi-Cloud PDF Storage Application

## Table of Contents
- [Overview](#overview)
- [Architecture](#architecture)
- [Features](#features)
- [Setup and Deployment](#setup-and-deployment)
  - [Prerequisites](#prerequisites)
  - [Deployment Steps](#deployment-steps)
- [More Information](#more-information)
- [Contributing](#contributing)
- [License](#license)

## Overview
This application serves as a robust, multi-cloud solution to manage PDF files. It leverages Google Cloud (GC) for Kubernetes and SQL operations while utilizing Amazon Web Services (AWS) S3 for Blob storage. Our infrastructure-as-code (IaC) tool of choice is Terraform, ensuring a consistent and reproducible infrastructure environment.

## Architecture
- **Google Cloud (GC)**: Hosts our Kubernetes cluster and SQL database.
- **Amazon Web Services (AWS) S3**: Utilized for storing PDF files as blobs.
- **Terraform**: Employs IaC practices to automate the provisioning of resources on both GC and AWS.

## Features
1. **Blob Storage for PDF**: The application supports the storage of PDF files as blobs in AWS S3.
2. **SQL Database**: Information related to the PDFs and other application data are stored in an SQL database hosted on Google Cloud.
3. **Multi-Cloud Strategy**: Ensuring robustness and flexibility by leveraging both Google Cloud and AWS.

## Setup and Deployment

### Prerequisites
- Terraform installed.
- Google Cloud SDK installed.
- AWS CLI installed and configured.



## Deployment Steps

### Terraform Initialization:
Run the following command in inside the terraform folder to create the database and AWS S3:
```bash
    terraform init
    terraform apply tcb_gcp_database.tf
    terraform apply tcb_aws_storage.tf
```

Configure the Kubernetes cluster inside GKE using Terraform:

```bash
    gcloud builds submit --tag gcr.io/<your project inside GKE>/luxxy-covid-testing-system-app-en
    kubectl apply -f luxxy-covid-testing-system.yaml
```



This project is licensed under the MIT License. See the LICENSE.md file for details.