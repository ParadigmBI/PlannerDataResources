Azure Planner Logic Apps
------------------------
This Logic Apps deployment template creates the bare bones for building a Microsoft Planner API using Azure API Management. The initial use case is to build a Power BI Data model.
Implement by:
* Create an Azure Resource Group
* Deploy Template
* Authorise connectors for Planner and AzureAD

Note: You must have permission to run PowerShell Scripts

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
  -TemplateFile $templateFile `
  -TenantId {_The tenant ID of the Azure Active Directory application_}

Then go into Azure web and authorise the connections by using 'Edit API Connection' on the connections

Other Files
-----------

Create the API as in the  video  on https://youtu.be/wOetvx9_d04

Load the DataFlow from file from PlannerDataFlow.json

See the blog at https://blog.paradigmbi.com.au/post/2021/06/15/planner-api-and-power-bi for more details.

When you connect PowerBI to the DataFlow will need the Columns and Measures in DataMeasuresandColumns.txt