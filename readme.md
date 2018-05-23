# FHIRBot 

FHIRBot is an Azure based conversational chatbot to interact with any FHIR DTSU3 compliant server,
to obtain or update medical record data using natural conversation and commands.

The FHIR Bot is presented as an art of the possible solution.  Security measures have been disabled to allow for public demonstration. 
## Public Demo Instructions
Note: The public demo is subject to frequent updates and periodic unavailability for maintenance/improvements.

1.	Pick a way to communicate with the BOT:

    + Add the bot to your skype contacts using this: https://join.skype.com/bot/ec960c92-8944-4dee-87db-c865e14bdc32 then start a skype message conversation with FHIRBot

    + If you want to show text conversation you need to start a text messaging thread to (please contact me for phone #), explain this is demo only, only some functionality can be exposed due to HIPPA might be more coming based on text messaging safe harbor guidance

    + You can use the following site to chat in any browser mobile or desktop: http://fhirbotwebuifree.azurewebsites.net/


2.	Bring up the following site in a separate browser window or another device:  https://fhirwatchtower.azurewebsites.net This monitors the FHIR Server for incoming updates and displays trends on weight, pulse, glucose.  It requires authentication with Microsoft Azure AD.  As long as you use Internet Explorer, Edge or Chrome (with Windows 10 account extension) you shouldn’t have to provide credentials.
  
3.  Select a patient on the left with which you are going to use as the subject for the bot conversation. (Either Dan,Fred Frog, or William Jones)

4.	Start a chat with the bot using your chosen method from above.  Start out by entering Hello/Hi or using Siri/Cortana to say Hello/Hi

5.	When prompted enter the PIN code for the patient you selected.  The PIN Codes are:
    + Dan   - 6786376490
    + Fred Frog – 8675309
    + William Jones - 555121

6.	The bot will greet you and you will have about 5 minutes of time to interact with BOT before it times out, you have to re-enter your PIN Code for security.
  
7.	Some things you can enter/say to the bot are:
    + “List doctors in Nashville” (Atlanta, Phoenix,Jacksonville,etc…) – Will show a list of providers with locations, general information link and/or schedule an appointment links.  On your mobile device  you can generally see map or dial number if you touch them in text messages or Web UI
     
    + “my pulse is X”  - Where X=heart rate in beats/minute.  The Bot Will chart a heart rate into the FHIR Server.  You will see this HR get charted into the FHIRServer watcher window within a few seconds, and trend lines will update
     
    + “I weigh X pounds/kilograms where X= weight in lbs or kg.  The BOT will chart a weight into the FHIR Server. You will see this weight get charted into the FHIRServer watcher window within a few seconds, and trend lines will update
     
    + “what is my plan of care” – You will see the latest complete care plan resource contained on the FHIR Server. (Currently patient Dan and William Jones are the only patients with a careplan)
     
    + “my blood sugar reading is X” - where X is your blood sugar in mg/Dl (e.g. 90)  it will also display your average and estimated A1C.  You will see this blood glucose  get charted into the FHIRServer watcher window within a few seconds, and trend lines will update
    + “what is my a1c” – Displays last a1c test results or average from glucose readings if no a1c available
    
8.	More things will be added frequently so try different queries as you please.

9.	When done enter or say Bye this will terminate the current session and remind you to delete the conversation for privacy. You can start another session by entering hello/hi again.


## Deploying your own HL7 FHIR Bot

1. [Create a BOT Web App Service](https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart)
2. [Import the FHIRClinical App into your LUIS (FHIRClinical.json file in this repo)](https://docs.microsoft.com/en-us/azure/cognitive-services/luis/create-new-app#import-new-app)
3. [In the Messaging App Service Created for your BOT change the deployment options to pull from this repo](https://docs.microsoft.com/en-us/azure/app-service/app-service-continuous-deployment#overview)
4. Obtain address to a DTSU3 compliant FHIR Server (URL,Authorization (if needed)). If you do not have access to a FHIR Server you can use the MSHLS Experimental Server. You can deploy it direct to Azure from [here](https://github.com/sordahl-ga/MSHLSFHIRServer)
5. Add the following App Settings/Values:
	```
	<add key="LUISURL" value="{Language Understand Service URL with Key/Options}" />
    <add key="FHIRServerAddress" value="{FHIR Server URL}" />
    <add key="FHIRAADTenant" value="{AAD Tenent}" />
    <add key="FHIRClientId" value="{FHIR Server Client Id}" />
    <add key="FHIRClientSecret" value="{FHIR Server Client Secret}" />
   ```

6. Try it out in your BOT's Tests Page in the Portal

## Authors

* **Steven Ordahl** - Microsoft HLS Apps and Infrastructure Cloud Architect
