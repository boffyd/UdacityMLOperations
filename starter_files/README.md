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

![Screen Shot 2021-05-22 at 5 03 30 pm](https://user-images.githubusercontent.com/72591620/119217758-b16ca600-bb1f-11eb-9536-92de84e25282.png)


An experiment was run with Classification, ensuring Explain best model is checked, and the Exit Criteria was changed to reduce the default (3 hours) to 1 and reduce the Concurrency from default to 5.  
![Screen Shot 2021-05-22 at 4 50 03 pm](https://user-images.githubusercontent.com/72591620/119217471-c34d4980-bb1d-11eb-93c9-963045469d5f.png)

![Screen Shot 2021-05-22 at 4 51 46 pm](https://user-images.githubusercontent.com/72591620/119217508-00194080-bb1e-11eb-8dc2-c8ff2b15332f.png)

![Screen Shot 2021-05-22 at 5 24 58 pm](https://user-images.githubusercontent.com/72591620/119218221-a36c5480-bb22-11eb-9cb6-86b12cb1c1d7.png)

The best performing model was VOTINGENSEMBLE
![Screen Shot 2021-05-22 at 5 25 27 pm](https://user-images.githubusercontent.com/72591620/119218233-b54df780-bb22-11eb-8466-6422cfc616c3.png)

![Screen Shot 2021-05-22 at 5 28 15 pm](https://user-images.githubusercontent.com/72591620/119218329-1a095200-bb23-11eb-9823-bc129926b622.png)


![Screen Shot 2021-05-22 at 5 26 06 pm](https://user-images.githubusercontent.com/72591620/119218252-cbf44e80-bb22-11eb-8dcb-4ea5181e1671.png)

![Screen Shot 2021-05-22 at 5 39 40 pm](https://user-images.githubusercontent.com/72591620/119218625-b41dca00-bb24-11eb-8c01-ea7091950280.png)


### Deploy the Best Model
After selecting the best model, the next step is to deploy the model so that we can provide an API URL.

This step involves deploying through the selected trained model using Azure Container Instance (ACI), with authentication enabled.  Deploying the model allows us to access the model enpoint.

![Screen Shot 2021-05-22 at 5 03 30 pm](https://user-images.githubusercontent.com/72591620/119218292-04942800-bb23-11eb-8ef4-a2652fcb9e39.png)

![Screen Shot 2021-05-22 at 5 03 30 pm](https://user-images.githubusercontent.com/72591620/119218631-bed85f00-bb24-11eb-8f8d-0b73cc9507c0.png)



### Enable Logging
The config.json file is downloaded and installed in the working directory to provide the appropriate subsription, resource ids etc for the work space which is used for logging.

Using gitbash as a terminal, the modified logs.py file which includes modifications to the original file to enable logging is run.  This triggers an authenticaiton process that is enabled/approved in a web browser.

![Screen Shot 2021-05-22 at 5 56 57 pm](https://user-images.githubusercontent.com/72591620/119219106-1b3c7e00-bb27-11eb-8485-10d46698f3e2.png)

![Screen Shot 2021-05-22 at 5 57 38 pm](https://user-images.githubusercontent.com/72591620/119219121-35765c00-bb27-11eb-8477-b8ec26722d64.png)

![Screen Shot 2021-05-22 at 5 55 37 pm](https://user-images.githubusercontent.com/72591620/119219074-eb8d7600-bb26-11eb-8c07-e342bff78251.png)






### Swagger Documentation
### Consume Endpoints
### Create and Publish a pipeline
### Documentation


## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.