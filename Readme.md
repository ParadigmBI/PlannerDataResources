Azure Planner Logic Apps
------------------------
This Logic Apps deployment template creates the bare bones for building a Microsoft Planner API using Azure API Management. The initial use case is to build a Power BI Data model.
Implement by:
* Create an Azure Resource Group
* Deploy Template
* Authorise connectors for Planner and AzureAD

Manual deployment from PowerShell:
>Connect-AzAccount

If you have more than one subscription you may want to:
	Set-AzContext {_subscription id_}
	
Create a resource group

>New-AzResourceGroup `
  -Name myResourceGroup `
  -Location "Australia East"

>$templateFile = {_location of LogicApp.json_}

>New-AzResourceGroupDeployment `
  -Name LogicApptemplate `
  -ResourceGroupName myResourceGroup `
  -TemplateFile $templateFile

Then go into Azure web and authorise the connections by using 'Edit API Connection' on the connections

