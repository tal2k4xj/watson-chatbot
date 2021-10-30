# Welcome to IBM Watson Assistant workshop !

Register to IBM Cloud: https://ibm.biz/BdfAtQ

### Step 1 - Create Watson Assistant service

[Watson Assistant](https://cloud.ibm.com/catalog/services/watson-assistant)

* Mark the licence agreements and click "Create"

* Click on "Launch Watson Assistant"

### Step 2 - Crete your assistant

* Click on "Create assistant"

* Enter the assistant name

* Click on "Add an action or dialog skill"

* Click on "Use sample skill"

* Select the blue "Customer Care Sample Skill" with the Type: Dialog

* Click on "Customer Care Sample Skill" below the Dialog section

### Step 3 - Try your assistant

* Click on "Try it" on the top right corner

* Talk with the chatbot and try to schedule an appointment

* Try to ask the chatbot different question during the schedule appointment process

### Step 4 - Add functionality with code using serverless application

* Select the "Dialog" section

* Click on "I want to make an appointment" node

* Click on "Customize"

* Enable "Callout to webhooks"

* Scroll down to "Then call out to my webhook" section inside the node

* Click on "Add parameter", enter
`key: date | value: "$date"`

* Click on "Add parameter", enter
`key: time | value: "$time"`

* Scroll down to "Assistant responds" section inside the node

* Remove the "true" respond

* Next to "$webhook_result_1" add the respond:
`"$webhook_result_1.message"`




### Step 5 - Use SPSS modeler flow

[SPSS Modeler flows](https://eu-gb.dataplatform.cloud.ibm.com/docs/content/wsd/spss-modeler.html?context=cpdaas&audience=wdp)

### Step 6 - Use dashboards

[Cognos dashboards](https://eu-gb.dataplatform.cloud.ibm.com/docs/content/wsj/getting-started/get-start-story.html?context=cpdaas&audience=wdp)