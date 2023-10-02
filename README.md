# Azure Portal Template for Tailscale 

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftailscale-acknowledge%2Ftailscale-arm-template%2Fmaster%2Fmain.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Ftailscale-acknowledge%2Ftailscale-arm-template%2Fmaster%2FcreateUiDefinition.json)

These templates will deploy a single tailscale linux server to Azure using the Azure Portal. The template allows deployment to a new Resource Group or existing Resource Group. To connect an existing vNET fill out the subnets in the Portal with the `tailscale Routed Subnets` option and peer the vNETs (if needed).
