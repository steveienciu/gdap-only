# BlueVoyant Sentinel RBAC Deployment

Deploys BlueVoyant SOC Entra group role assignments on an **existing** Microsoft Sentinel resource group.

Use this when the client already has:

- Azure Lighthouse onboarded
- A Log Analytics workspace with Microsoft Sentinel enabled
- Standard data connectors and workspace settings configured

This template does **not** create a resource group, workspace, connectors, Lighthouse delegation, or other Sentinel content. It only runs `LinkedTemplates/bluevoyantRgRoleAssignments.json`.

## Deploy to Azure

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsteveienciu%2Fgdap-only%2Fmain%2Fazuredeploy.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Fsteveienciu%2Fgdap-only%2Fmain%2FcreateUiDefinition.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton""/>
</a>
