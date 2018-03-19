# FHIRBot 

FHIRBot is an Azure based conversational chatbot to interact with any FHIR DTSU3 compliant server,
to obtain or update medical record data using natural conversation and commands.

The FHIR Bot is presented as an art of the possible solution.  Security measures have been disabled to allow for public demonstration. 

## Getting Started

1. Create a BOT Web App Service https://docs.microsoft.com/en-us/bot-framework/bot-service-quickstart
2. In the Messaging App Service Created for your BOT change the deployment options to pull from this repo.
3. Add the following App Settings/Values:
	<add key="LUISURL" value="{Language Understand Service URL with Key/Options}" />
    <add key="FHIRServerAddress" value="{FHIR Server URL}" />
    <add key="FHIRAADTenant" value="{AAD Tenent}" />
    <add key="FHIRClientId" value="{FHIR Server Client Id}" />
    <add key="FHIRClientSecret" value="{FHIR Server Client Secret}" />
4. Try it out in your BOT's Tests Page in the Portal

## Authors

* **Steven Ordahl** - Microsoft HLS Apps and Infrastructure Cloud Architect
