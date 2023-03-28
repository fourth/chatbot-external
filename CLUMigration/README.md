## CLU Migration

This sample shows how to integrate Conversational Language Understanding (CLU) in Bot Framework Composer using the CluRecognizer package (developed by Orestis from Microsoft). The main goals are:

* Intent recognition triggers (PizzaOrder, DeliveryLocation) and entity extraction within them (e.g. DeliveryLocation - @geography.text)
* User input validation using CLU (see: CluEntityValidator dialog) and entity extraction (in the same dialog: dialog.predictionEntity.text)

Prerequisites:

In order to run the Composer project, you need to create your own Conversational Language Understanding resources by:

### 1. Import the PizzaOrdering project, train model and add deployment

1.1 Import the [PizzaOrdering project](CLUMigration/clu-projects/PizzaOrdering.json) located in clu-projects folder

You should import the PizzaOrdering.json into your Language Studio

1.2. Start a training job

1.3. Add deployment

1.4. Test the deployment


### 2. Copy and paste configuration values

#### 2.1. Copy configuration values

Nagivate to "Deploying a model" - select your deployment - click on "Get Prediction URL" tab and copy:

Prediction URL

From Sample request section copy:

projectName
deploymentName
Ocp-Apim-Subscription-Key


#### 2.2. Paste configuration values

2.2.3. Main dialog CLUMigration

Click on the main dialog: CLUMigration and on the right-side under "Recognizer/Dispatch type" paste them


Prediction URL -> leave only the base url (e.g. https://subdomain-here.cognitiveservices.azure.com)

projectName -> projectName

Ocp-Apim-Subscription-Key -> endpointKey

deploymentName -> deploymentName


2.2.4. CluEntityValidator dialog

Click on dialog "CluEntityValidator" - then on the first action "Send an HTTP request" and paste the properties:

Prediction URL -> Url

In the Body section - parameters object:

projectName -> projectName

deploymentName -> deploymentName

In the Headers section:

For Key: Ocp-Apim-Subscription-Key Value -> paste the value of: Ocp-Apim-Subscription-Key
