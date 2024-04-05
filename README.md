# Azure MLOps (v2) Training

This repo is practice repo for Community IP MLOps In a Day workshop. The goal is to have the participants to build a traing and a deployment pipeline
## Repo structure 

```bash
├── ci-cd - examples of using Azure DevOps Pipeline and Github Action to orchastrate CI CD pipelines
│   ├── azure-pipelines - code samples for using Azure DevOps Pipeline
│   │   ├── cli - cli code samples
│   │   ├── sdk - sdk code samples
│   ├── dev-requirements.txt - Conda requirement file
│   ├── setup-cli.sh - Command to prepare Azure Pipeline for Azure ML CLI
│   ├── setup-sdk.sh - Command to prepare Azure Pipeline for Azure ML SDK (Testing)

├── data
│   ├── taxi-data.csv - data used for training & testing ML model
│   ├── taxi-batch.csv - data used as input for testing batch endpoint
│   ├── taxi-request.json - data used as input for testing online endpoint

├── component - python scripts of ML workload
│   ├── prep
│   |   ├── prep.py - python script that reads raw data and prepare train, val and test datasets
│   |   ├── test_prep.py - python script used when unit testing `prep.py` 
│   ├── train
│   |   ├── train.py - python script that reads train data, trains and saves an ML model
│   |   ├── test_train.py - python script used when unit testing `train.py` 
│   ├── evaluate
│   |   ├── evaluate.py - python script that reads test data and trained model and evaluates model performance
│   |   ├── test_evaluate.py - python script used when unit testing `evaluate.py` 
│   ├── register
│   |   ├── register.py - python script that register trained model in AzureML Model Registry
│   |   ├── test_register.py - python script used when unit testing `register.py` 
├── environment - environments needed execute ML workload
│   ├── train-conda.yml - environment conda specification needed to execute python scripts in ML workload
├── components - AzureML Components definitions
│   ├── prep.yml - AzureML Component definition for `prep.py` 
│   ├── train.yml - AzureML Component definition for `train.py` 
│   ├── evaluate.yml - AzureML Component definition for `evaluate.py` 
│   ├── register.yml - AzureML Component definition for `register.py` 
├── ml-pipelines
│   ├── cli - CLI training/deployment pipeline exercise
│   │   ├── deploy - deploy pipeline assets
│   │   │   ├── batch - deploy batch pipeline assets
│   │   │   │   ├── batch-deployment.yml - deploy batch deployment template
│   │   │   │   ├── batch-endpoint.yml - deploy batch endpoint template
│   │   │   ├── online - deploy online pipeline assets
│   │   │   │   ├── online-deployment.yml - deploy online deployment template
│   │   │   │   ├── online-endpoint.yml - deploy online endpoint template
│   │   ├── train - training pipeline assets
│   │   |   ├── compute.yml - yaml configuration of AzureML training compute cluster
│   │   |   ├── data.yml - yaml configuration of AzureML training (input) data asset
│   │   |   ├── environment.yml - AzureML yaml configuration of training environment
│   │   |   ├── pipeline.yml - AzureML yaml configuration of training pipeline
│   │   |   ├── pipeline_automl.yml - AzureML yaml configuration of training pipeline
│   │   ├── azureml-cliv2.ipynb - CLI training/deployment pipeline notebook code sample
│   │   ├── train.sh - training pipeline CLI (Lab 01)
│   │   ├── deploy-batch-endpoint.ipynb - deploy batch pipeline notebook (Lab 02)
│   │   ├── deploy-online-endpoint.ipynb - deployment online pipeline notebook (Lab 02)
│   ├── sdk - SDK training/deployment pipeline exercise
│   │   ├── train-sdkv2.ipynb - training pipeline SDK (Lab 01)
│   │   ├── deploy-batch-endpoint-sdkv2.ipynb - deploy batch pipeline notebook (Lab 02)
│   │   ├── deploy-online-endpoint0sdkv2.ipynb - deployment online pipeline notebook (Lab 02)
```

## MLOps v2 Lab

In this workshop, we provided both CLI and SDK exercise. You can choose your preferred option. The exercise starts from ml-pipeline folder. 

There are 2 labs in this workshop:

## Lab 1. Building a training pipeline. It can be a custom model pipeline or automl pipeline.
  - Experiment with notebooks in `notebooks` folder to explore data and model 
  - Build pipeline by navigating to `ml-pipelines` cli or sdk and running corresponding notebooks
  - Review components of the pipeline and fill in missing parts and references 
  - Once pipeline is run, Model will be trained and registered in the WS registry

## Lab 2. Building a deployment pipeline, it could either a online endpoint or batch online. 
  - Deploy Model by navigating to `ml-pipelines` cli or sdk and running corresponding notebooks
  - In this lab, we also provided ci-cd folder to demonstrate Azure Pipeline or Github action orchestration of CI/CD pipeline. 
    - For GH Actions follow https://github.com/lenisha/mlops-v2-workshop/blob/main/ci-cd/README-GH.md
   
## Hands-on End-to-end machine learning operations (MLOps) with Azure Machine Learning
  - Learn via hands-on workshop: https://learn.microsoft.com/en-us/training/paths/build-first-machine-operations-workflow/






