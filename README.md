# Udacity_AzureMLProject2
# Operationalizing Machine Learning
This is Udacity Azure Machine Learning Nanodegree project 2, I've worked with the Bank Marketing dataset which contains 21 features and the goal is to predict if a person will take a loan or not. The target column is y.
In this project using Microsoft Azure we will configure a cloud-based Machine Learning model, deploy it, and consume it. We will also create, publish, and consume a pipeline using Azure Python SDK.
![image](https://user-images.githubusercontent.com/62311350/115136408-2dfdf780-a03d-11eb-9e4f-89ae6edcf171.png)
 
Project main steps:
In this project, we will be following the below steps:
Authentication:
In this step, we need to create a Security Principal (SP) to interact with the Azure Workspace.Here I’m using the lab Udacity provided to me, so I have skipped this step as I’m are not authorized to create a security principal.
Automated ML Experiment
In this step, we create an experiment using Automated ML, configure a compute cluster, and use that cluster to run the experiment.
First, we need to use the Bank Marketing dataset (bankmarketing_train.csv) that is provided to Azure Machine Learning Studio.
Link: 
https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv

![image](https://user-images.githubusercontent.com/62311350/115136443-8208dc00-a03d-11eb-8daa-32802989b620.png)
![image](https://user-images.githubusercontent.com/62311350/115136448-87febd00-a03d-11eb-896a-e9218fe7638a.png)

The best algorithm found is VotingEnsemble with an accuracy of 91.8%.

 ![image](https://user-images.githubusercontent.com/62311350/115136456-951bac00-a03d-11eb-8948-d39d9dd31562.png)

Deploy the best model
To interact with the best model obtained we have to deploy it using Azure Container Instance (ACI) and authentication is enabled.

 ![image](https://user-images.githubusercontent.com/62311350/115136470-9fd64100-a03d-11eb-9f6d-878a1ae54acb.png)
![image](https://user-images.githubusercontent.com/62311350/115136475-a5338b80-a03d-11eb-8a7f-6b71e00bdb51.png)
![image](https://user-images.githubusercontent.com/62311350/115136476-aa90d600-a03d-11eb-9a14-1ddc38b58079.png)
![image](https://user-images.githubusercontent.com/62311350/115136479-b11f4d80-a03d-11eb-8d12-06521dcbb9dc.png)
![image](https://user-images.githubusercontent.com/62311350/115136489-ba101f00-a03d-11eb-8f81-353b5be08771.png)

 Enable logging 
We enable application insights in logs.py and then run the script to view the logs generated.

![image](https://user-images.githubusercontent.com/62311350/115136497-c5634a80-a03d-11eb-803e-4c284e1f5b75.png)
![image](https://user-images.githubusercontent.com/62311350/115136504-cb592b80-a03d-11eb-9dfb-bd574ab68530.png)
  
 
Swagger Documentation
Swagger is a tool that eases the documentation efforts of HTTP APIs. It makes it easier to explain what type of GET and POST requests. For consuming our best AutoML model using Swagger, we first need to download the swagger.json file provided to us in the Endpoints section of Azure Machine Learning Studio.  

 ![image](https://user-images.githubusercontent.com/62311350/115136510-d4e29380-a03d-11eb-9dc5-9943e40fd05f.png)
![image](https://user-images.githubusercontent.com/62311350/115136515-dc09a180-a03d-11eb-9016-38b7e2726a6b.png)
![image](https://user-images.githubusercontent.com/62311350/115136518-de6bfb80-a03d-11eb-9872-0aace32af5e8.png)

After running the script, we can find our best model's documentation instead of the default Swagger page.
Consume model endpoints
Finally, we can now interact with the model and feed some test data to it by adding the scoring_uri and the key to the endpoint.py script and running it. So once a model has been deployed, an endpoint will be available which allows user to send inputs to the trained
model and get a response back. This is called as consuming deployed service.

 ![image](https://user-images.githubusercontent.com/62311350/115136526-e75ccd00-a03d-11eb-96ab-eeb781f65628.png)

Benchmarking means setting a baseline as an acceptable performance measure. Here we use apache benchmark to see the model performance against our HTTP requests.

 ![image](https://user-images.githubusercontent.com/62311350/115136528-eaf05400-a03d-11eb-8924-cc5de8906ad3.png)

Create and publish a pipeline
Publishing a pipeline is the process of making a pipeline publicly available and to automate workflows.

![image](https://github.com/tejasbangera/Udacity_AzureMLProject2/blob/main/SS213.png)
![image](https://github.com/tejasbangera/Udacity_AzureMLProject2/blob/main/SS214.png)
![image](https://github.com/tejasbangera/Udacity_AzureMLProject2/blob/main/SS215.png)
![image](https://github.com/tejasbangera/Udacity_AzureMLProject2/blob/main/SS216.png)

We can also view the graph of pipeline endpoint and also its active status:

Screen Recording:

Screen Recording Link: https://youtu.be/lS_pDtDVbTs

[![Watch the video](https://i.imgur.com/vKb2F1B.png)](https://github.com/tejasbangera/Udacity_AzureMLProject2/blob/main/Recording%20%234.mp4)

Future Improvements:

We can try with Deep Learning for better performance.

Resampling or adding more data can resolve class-imbalance issue and improve accuracy.
.
