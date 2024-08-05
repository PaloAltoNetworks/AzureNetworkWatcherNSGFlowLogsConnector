This project installs into an Azure Function in your Azure subscription. Its job is to read NSG Flow Logs from your configured storage account, break the data into chunks that are the right size for your log analytics system to ingest, then transmit the chunks to that system.

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FPaloAltoNetworks%2FAzureNetworkWatcherNSGFlowLogsConnector%2Fmaster%2FNwNsgProject%2Fdeploy.json)


# Settings

In the Application Settings of your Azure Function:
* AppName                     - this is the name of the function app. In the Azure Portal, this is the name that will appear in the list of resources.  
   Example: ```MyNSGApp```  
* appServicePlan              - "ServicePlan" or "Consumption".  
   If you select "ServicePlan", an App Service Plan will be created and you will be billed accordingly. If you select "Consumption", you will be billed based on the Consumption plan.  
* appServicePlanTier          - "Free", "Shared", "Basic", "Standard", "Premium", "PremiumV2"  
   Example: ```Standard```  
   (only relevant for ServicePlan)  
* appServicePlanName          - depends on tier, for full details see "Choose your pricing tier" in the portal on an App service plan "Scale up" applet.  
   Example: For standard tier, "S1", "S2", "S3" are options for plan name  
   (only relevant for ServicePlan)  
* appServicePlanCapacity      - how many instances do you want to set for the upper limit?  
   Example: For standard tier, S2, set a value from 1 to 10  
   (only relevant for ServicePlan)  
* githubRepoURL                     - this is the URL of the repo that contains the function app source. You would put your fork's address here.  
   Example: ```https://github.com/PaloAltoNetworks/AzureNetworkWatcherNSGFlowLogsConnector```
* githubRepoBranch                  - this is the name of the branch containing the code you want to deploy.  
   Example: ```master```  
* nsgSourceDataConnection     - a storage account connection string  
   Example: ```DefaultEndpointsProtocol=https;AccountName=yyy;AccountKey=xxx;EndpointSuffix=core.windows.net```
* xdrHost - XDR HTTP collector endpoint
* xdrToken - XDR HTTP collector token
