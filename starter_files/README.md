*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.


# Operationalising Machine Learning

This project aims to implement a machine learning pipeline through the following key steps (as illustrated through the Architectural Diagram) to classify a banking data set as provided through the UCI depository for a classification model.
* Authentication
* AutoML Model
* Deploy the Best Model
* Enable Logging
* Swagger Documentation
* Consume Endpoints
* Create and Publish a pipeline
* Documentation

## Architectural Diagram
The following image illustrates the proposed architecture for the project.
![Screen Shot 2021-05-22 at 4 14 48 pm](https://user-images.githubusercontent.com/72591620/119216745-d9a4d680-bb18-11eb-8dcd-5f071daa4037.png)

* Authentication: Create a Security Protocol within the Azure Workspace
* AutoML Model: Use AutoML to compare suitable models against the preferred classification metric
* Deploy the Best Model: Once the best model is selected, it is then deployed
* Enable Logging: Logging for use and potential errors through out its deployment
* Swagger Documentation: 
* Consume Endpoints: 
* Create and Publish a pipeline: The process is automated using a pipeline.
* Documentation

## Key Steps
### Authentication
This step was not used as the Udacity VM account was used for modelling.

### AutoML Model
The intial step included creating a compute cluster using the Standard_DS12_v2 for teh Virtual Machine with 1 as the minimum number of nodes.

The dataset provided, was located from the UCI depository as per the attached link.
https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv

The dataset consists of 20 variables including numeric (integer and decimal) and categorical (strings) and one target variable "y" which is a categorical variable for classification indicating whether or not the target applicant was given a loan.

The dataset was loaded into Azure Machine Learning as a tabular dataset.

![Screen Shot 2021-05-22 at 4 47 21 pm](https://user-images.githubusercontent.com/72591620/119217411-62be0c80-bb1d-11eb-86c6-57077d0d93d3.png)

An experiment was run with Classification, ensuring Explain best model is checked, and the Exit Criteria was changed to reduce the default (3 hours) to 1 and reduce the Concurrency from default to 5.  
![Screen Shot 2021-05-22 at 4 50 03 pm](https://user-images.githubusercontent.com/72591620/119217471-c34d4980-bb1d-11eb-93c9-963045469d5f.png)

![Screen Shot 2021-05-22 at 4 51 46 pm](https://user-images.githubusercontent.com/72591620/119217508-00194080-bb1e-11eb-8dc2-c8ff2b15332f.png)

### Deploy the Best Model
The AutoML portion was set to run for some time whilst it ran through its process.  The best model was then chosen to deploy.



### Enable Logging
### Swagger Documentation
### Consume Endpoints
### Create and Publish a pipeline
### Documentation


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
