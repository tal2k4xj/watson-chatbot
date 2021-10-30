# Welcome to IBM Watson Assistant workshop !

Register to IBM Cloud: https://ibm.biz/BdfAtQ

Recorded session: https://www.crowdcast.io/e/chatbot

### Step 1 - Create Watson Assistant service

[Watson Assistant](https://cloud.ibm.com/catalog/services/watson-assistant)

1. Mark the licence agreements and click "Create"

2. Click on "Launch Watson Assistant"

### Step 2 - Crete your assistant

1. Click on "Create assistant"

2. Enter the assistant name

3. Click on "Add an action or dialog skill"

4. Click on "Use sample skill"

5. Select the blue "Customer Care Sample Skill" with the Type: Dialog

6. Click on "Customer Care Sample Skill" below the Dialog section

### Step 3 - Try your assistant

1. Click on "Try it" on the top right corner

2. Talk with the chatbot and try to schedule an appointment

3. Try to ask the chatbot different question during the schedule appointment process

### Step 4 - Add functionality with code using serverless application

1. Select the "Dialog" section

2. Click on "I want to make an appointment" node

3. Click on "Customize"

4. Enable "Callout to webhooks"

5. Scroll down to "Then call out to my webhook" section inside the node

6. Click on "Add parameter", enter
`key: date | value: "$date"`

7. Click on "Add parameter", enter
`key: time | value: "$time"`

8. Scroll down to "Assistant responds" section inside the node

9. Remove the "true" respond

10. Next to "$webhook_result_1" add the respond:
`"$webhook_result_1.message"`

11. Go to [IBM Functions](https://cloud.ibm.com/functions/actions) and click "Create"
	* note - if you cant create action you might need to create namespace before on the top side of your screen

12. Give your action a name, select Python 3.7 runtime and click "Create"

13. Copy & replace the code:
`import sys

def main(dict):
    return { 'message': 'Your appointment scheduled for {0} at {1}'.format(dict["date"],dict["time"]) }` 

14. Click "save"

15. Go to "Endpoints"

16. Mark the "Enable as Web Action"

17. Click "save"

18. Copy the public url

19. Go back to the Watson Assistant tool and select "Webhooks" under the "Options" section on the left side menu

20. Paste the public url and add the suffix ".json" to it

21. Try to schedule appointment again

### Step 5 - Understand special functions

1. Go to "#General_Greetings" node inside the Dialog

2. You can find there the "now()" function bein used, to learn more about those special functions go to [Expression language methods](https://cloud.ibm.com/docs/assistant?topic=assistant-dialog-methods#dialog-methods-date-time)

### Step 6 - Defining contextual entities

1. Select "My Entities" under "Entities" section

2. Click on "Create Entity"

3. Enter entity name (you can use "name")

4. Click on "Create Entity"

5. Add you name as an example and click on "Add value"

6. Go back to "Intents" section

7. Click on "Create Intent"

8. Enter intent name (you can use "my_name")

9. Click on "Create Intent"

10. Add the following examples:
	* Hi! My name is What? My name is Who? My name is Chika-chika Slim Shady
	* Im James
	* Im the great Mary
	* Is Robert
	* Its Sarah
	* Its me John
	* My name is David
	* They call me Linda
	* You can call me William
	* you should call me Elizabeth
	* Haim is my name
	* Moshe it is

11. Enable the "Annotate entities" just above the examples you added

12. Now select every name in the examples and mark it as @name (the entity name)

13. After you done, go back to the "Dialog" section

14. Click on "Add node"

15. Add to the condition "If assistant recognizes" the value `#my_name`

16. Add a responde under "Assistant responds" with the following text:
`Your name is <? @name ?>`

### Step 7 - Other options and analytics

* Go to the following sections and read more about them:
	* [Disambiguation](https://cloud.ibm.com/docs/assistant?topic=assistant-dialog-runtime#dialog-runtime-disambiguation)
	* [Autocorrection](https://cloud.ibm.com/docs/assistant?topic=assistant-dialog-runtime-spell-check)
	* [Intent detection](https://cloud.ibm.com/docs/assistant?topic=assistant-intent-detection)
	* [Analytics](https://cloud.ibm.com/docs/assistant?topic=assistant-logs-overview)

















