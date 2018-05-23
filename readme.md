# FHIRBot 

FHIRBot is an Azure based conversational chatbot to interact with any FHIR DTSU3 compliant server,
to obtain or update medical record data using natural conversation and commands.

The FHIR Bot is presented as an art of the possible solution.  Security measures have been disabled to allow for public demonstration. 

## Getting Started

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
