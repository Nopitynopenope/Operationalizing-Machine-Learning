

# Operationalizing Machine Learning

This project is part of the Udacity Azure ML Nanodegree. The primary aim of the project is to Operationalize Machine Learning and put it to use. We create, deploy and consume an AutoMl model and also create, publish and consume a pipeline. 


# Overview
This dataset ("https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv") contains data about 32950 individuals. The data includes their age, marital status, education, housing, loans, contact etc. We first use Azure AutoMl tool on the dataset provided to find the best model based on the metrics (like Accuracy). We then deploy the model and consume it and check the performance using Application Insights. Later, we create, publish and consume a pipeline using Jupyter Notebook.

## Architectural Diagram

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/Screenshots/architechture.png?raw=true "Architechture Diagram")

**Authentication**

Authentication is crucial for the continuous flow of operations. Continuous Integration and Delivery system (CI/CD) rely on uninterrupted flows. When authentication is not set properly, it requires human interaction and thus, the flow is interrupted. An ideal scenario is that the system doesn't stop waiting for a user to input a password. So whenever possible, it's good to use authentication with automation.

**Authentication types**

**Key- based**

Azure Kubernetes service enabled by default
Azure Container Instances service disabled by default

**Token- based**

Azure Kubernetes service disabled by default
Not support Azure Container Instances

**Interactive**

Used by local deployment and experimentation (e.g. using Jupyter notebook)


**Azure AutoML**

Automated machine learning, also referred to as automated ML or AutoML, is the process of automating the time consuming, iterative tasks of machine learning model development. It allows data scientists, analysts, and developers to build ML models with high scale, efficiency, and productivity all while sustaining model quality.

In this project we use AutoMl  to find the model that provides the most accurate results. In this case, it was Voting Ensemble with _0.91958 accuracy._


**Deploy**

Deployment is about delivering a trained model into production so that it can be consumed by others. Configuring deployment settings means making choices on cluster settings and other types of interaction with a deployment. Having a good grasp on configuring production environments in Azure ML Studio and the Python SDK is the key to get robust deployments.

In this project, we deploy the best model, Voting Ensemble, with Azure Container Instances and we enable authentication.


**Enable Application Insights**

Application Insights collects log, performance, and error data. By automatically detecting performance anomalies and featuring powerful analytics tools, you can more easily diagnose issues and better understand how your functions are used. These tools are designed to help you continuously improve performance and usability of your functions. You can even use Application Insights during local function app project development. 

In this project we run one of the starter files logs.py in order to enable Application Insights.


**Consume Endpoints**

Swagger is a tool that helps build, document, and consume RESTful web services like the ones you are deploying in Azure ML Studio. It further explains what types of HTTP requests that an API can consume, like POST and GET.

You can consume a deployed service via an HTTP API. An HTTP API is a URL that is exposed over the network so that interaction with a trained model can happen via HTTP requests.

Users can initiate an input request, usually via an HTTP POST request. HTTP POST is a request method that is used to submit data. The HTTP GET is another commonly used request method. HTTP GET is used to retrieve information from a URL. The allowed requests methods and the different URLs exposed by Azure create a bi-directional flow of information.

In  this project we us ethe starter file endpoint.py to consume the endpoint of the deployed model. We send two input queries and we get appropriate response.


**Create a Pipeline**

This is the most common Python SDK class you will see when dealing with Pipelines. Aside from accepting a workspace and allowing multiple steps to be passed in, it uses a description that is useful to identify it later.

**Publish pipelines**

Publishing a pipeline is the process of making a pipeline publicly available. You can publish pipelines in Azure Machine Learning Studio, but you can also do this with the Python SDK.

When a Pipeline is published, a public HTTP endpoint becomes available, allowing other services, including external ones, to interact with an Azure Pipeline.

Pipelines can perform several other tasks aside from training a model. Some of these tasks, or steps are:

1.  Data Preparation
2.  Validation
3.  Deployment
4.  Combined tasks


## Key Steps



**Dataset**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(96).png?raw=true "")


**AutoMl-Run**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(65).png?raw=true "")


**AutoMl-Run The best model**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(66).png.png?raw=true "")


**Voting Ensemble**- The best model is deployed using Azure Container Instances and Authentication is Enabled

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(67).png?raw=true "VotingEnsemble")


**Best Model Explanation**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(83).png?raw=true "")

**Best Model Explanation**- Aggregate plots

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(84).png?raw=true "")


**Explanation- Feature Importance**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(85).png?raw=true "")


**Explanation- Datapoints**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(87).png?raw=true "")


**Deploy**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(68).png?raw=true "")


**Model Deployed- Basic Consumption Info**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(72).png?raw=true "")


**logs.py execution**

We use logs.py to Enable Application Insights

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(70).png?raw=true "")


**Applications Insight Enabled**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(80).png?raw=true "")


**Application Insights**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(88).png?raw=true "")


![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(89).png?raw=true "")


**Directory Listing**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(74).png?raw=true "")

**Running swagger.sh and serve.py**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(73).png?raw=true "")


**endpoint.py and benchmark.sh Execution**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(78).png?raw=true "")


**Performance Tracking**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(79).png?raw=true "")


**Swagger- localHost**

![Alt text]( https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(76).png?raw=true "")


**Swagger Input Description**
![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(77).png?raw=true "")


**Swagger Responses**
![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(82).png?raw=true "")


**Pipeline RunDetails Widget**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(93).png?raw=true "")


**Pipeline Publishing**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(90).png?raw=true "")


**Published Pipeline**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(91).png?raw=true "")


**Endpoint of the Pipeline**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(92).png?raw=true "")


**Pipeline Runs**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(97).png?raw=true "")


**Pipeline Endpoints**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(98).png?raw=true "")


**Jupyter Notebook**

![Alt text](https://github.com/MonishkaDas/nd00333_AZMLND_C2/blob/master/starterfile1/ScreenShots/Screenshot%20(95).png?raw=true "")




## Screen Recording

Link to the screencast: https://www.youtube.com/watch?v=Byf4chPwAuw

The screencast highlights the significant aspects of the project. It starts with diplaying the dataset in the datasets tab. Then, we check the AutoML Experiments tab and find the AutoMl run. We find the best model to be VotingEnsemble and check the explanation provided and the conclusions drawn from the experiment. We then move to the models section to find the deployed model 'bank-marketing-model-deploy'. We check thta the application insights in enabled and visit the link. We then run endpoint.py, benchmark.py and serve.py in the terminal. We launch the localhost to check the swagger documentation of our model. We then move to the pipelines section. The pipeline runs and endpoints are checked and we run through the jupyter notebook provided.

## Future Work

Working on this project has been a rewarding experience. I look forward to working with Azure and checking even more of the salient features that it has to offer. I will explore different techniques, like regularization, cross validation, data cleaning as well as using only some of the features, and check how I can deploy the best possible model for each case. Furthermore, I will study the exceptions in detail so as to publish a service that works and shows appropriate results for every query. 
