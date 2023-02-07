# Operationalizing Machine Learning

## Overview
This is an overview of the project Operationalizing Machine Learning for the course Machine Learning Engineering with Azure on Udacity.
We have created a AutoML job using banking dataset and deployed the best model from the job. We used the model endpoint to post a payload and get predit back. We also learned 
to create, publish, and consume a pipeline.

## Architectural Diagram
*Figure 1: Architecture
![Architectural Diagram](screenshots/Architecture.png)

## Key Steps
**1. Authentication :** 

I skipped this step as I was using the lab Udacity account.

**2. Automated ML Experiment :** 

I configured a compute cluster (Standard_DS3_v2), registered the bank marketing dataset
and set up and ran an Automated ML experiment (best-model). This experiment identified VotingEnsemble to be the best 
model with a weighted AUC of 0.95. 

*Figure 2: Registered Dataset*

As can be seen in the figure, the *bankmarketing_train.csv* was successfully uploaded as a registered dataset named 
*bank-marketing*.
![Registered Dataset](screenshots/Fig 1.png)

*Figure 4: Experiment Completion*

As can be seen in the figure the AutoML experiment called best-model has completed in about 18 mins and the VotingEnsemble
was the best model found.
![Experiment Completion](images/Step2-ExperimentCompletion.png)

*Figure 5: AutoML Models*

The figure shows all the models evaluated by the AutoML experiment and their corresponding weighted AUCs.
![Step 2 - Best Model 1](images/Step2-BestModel1.png)

*Figure 6: Best AutoML Model Metrics*

The figure shows the metrics for the best model (VotingEnsemble). 
![Step 2 - Best Model 1](images/Step2-BestModel2.png)

**3. Deploy the best model :** 

I deployed the best model using Azure Container Instance (ACI) with authentication enabled. 

*Figure 7: Model Deployment*

The figure shows the settings used to deploy the model.
![Model Deployment](images/Step3-ModelDeployment.png)

**4. Enable logging :**

I created a virtual conda environment and installed the Python SDK for Azure.
I edited and ran the provided *logs.py* to enable logging. This helped monitor the deployed model and keep track of the
request frequency, latency, etc.

*Figure 8: Application Insights Enabled*

The figure shows the model endpoint page which has been updated to reflect that application insights are now enabled.
![Application Insights Enabled](images/Step4-ApplicationInsightsEnabled.png)

*Figure 9: Running Logs*

The figure shows the endpoint logs running in the terminal.
![Running Logs](images/Step4-RunningLogs.png)

**5. Swagger Documentation :**

I downloaded *swagger.json* and ran both *swagger.sh* and *serve.py*. I interacted
with the swagger instance running with the documentation for the HTTP API for the model.

*Figure 10: Serving Swagger Directory*

The figure shows the swagger directory is being served with *serve.py*.
![Serving Swagger Directory](images/Step5-Serve.png)

*Figure 11: Swagger UI Container*

The figure shows the running docker container which was built on the swagger-ui image.
![Swagger UI Container](images/Step5-SwaggerUIDockerContainer.png)

*Figure 12: Swagger API*

The figure shows the Swagger API page for the required model deployment endpoint.
![Swagger API](images/Step5-SwaggerAPI.png)

**6. Consume model endpoints :**

I successfully demonstrated the model was consumable by modifying and running *endpoint.py*. I also demonstrated I 
could consume the model using Postman.

*Figure 13: Consume Model*

The figure shows the model is returning predictions when the updated *endpoint.py* is run. This demonstrates the model can be 
consumed by posting a JSON to the endpoint and supplying the required authentication.

![Consume Model](images/Step6-ConsumeModel.png)

*Figure 14: Consume Model Via Postman*

The figure shows the model is consumable by using the *Postman* desktop application.
![Consume Model Postman](images/Step6-ConsumeModelPostman.png)

**7. Create and publish a pipeline :** 

I uploaded and updated the jupyter notebook provided to match the environment. I 
demonstrated it was running successfully.

*Figure 15: Pipeline Running*

The figure shows the pipeline has been submitted from the Jupyter notebook and is now running with information available in ML studio. 
![Pipeline Running](images/Step7-PipelineRunning.png)

*Figure 16: Pipeline Completion Notebook*

The figure shows the pipeline run has completed in the Jupyter notebook.
![Pipeline Completion Notebook](images/Step7-PipelineCompletion1.png)

*Figure 16: Pipeline Completion*

The figure shows the pipeline has completed as shown in ML studio.
![Pipeline Completion](images/Step7-PipelineCompletion2.png)

*Figure 16: Published Pipeline*

The figure shows the published pipeline in ML studio.
![Published Pipeline](images/Step7-PublishedPipeline.png)

*Figure 16: Published Pipeline Endpoint*

The figure shows the published pipeline endpoint in ML studio.
![Published Pipeline Endpoint](images/Step7-PublishedPipelineEndpoint.png)




## Screen Recording
[https://youtu.be/97uhnickb0M](https://youtu.be/97uhnickb0M)


