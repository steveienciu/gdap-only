# BlueVoyant Sentinel RBAC Deployment

Deploys BlueVoyant SOC Entra group role assignments on an **existing** Microsoft Sentinel resource group.

Use this when the client already has:

- Azure Lighthouse onboarded
- A Log Analytics workspace with Microsoft Sentinel enabled
- Standard data connectors and workspace settings configured

This template does **not** create a resource group, workspace, connectors, Lighthouse delegation, or other Sentinel content. It only runs `LinkedTemplates/bluevoyantRgRoleAssignments.json`.

## Deploy to Azure

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsteveienciu%2FSentinelStuff%2Fmain%2Fazuredeploy.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2Fsteveienciu%2FSentinelStuff%2Fmain%2FcreateUiDefinition.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>

## Prerequisites

- An existing resource group containing the Sentinel workspace
- Deployer has **Owner** or **User Access Administrator** on that resource group (required to create role assignments)

## Azure CLI

```bash
az deployment sub create \
  --location "<region>" \
  --template-uri "https://raw.githubusercontent.com/steveienciu/SentinelStuff/main/azuredeploy.json" \
  --parameters rgName="<existing-rg-name>"
```

Or deploy the linked template directly at resource group scope:

```bash
az deployment group create \
  --resource-group "<existing-rg-name>" \
  --template-uri "https://raw.githubusercontent.com/steveienciu/SentinelStuff/main/LinkedTemplates/bluevoyantRgRoleAssignments.json"
```

## Role assignments

See metadata in [LinkedTemplates/bluevoyantRgRoleAssignments.json](LinkedTemplates/bluevoyantRgRoleAssignments.json) for the Entra groups and roles assigned.
