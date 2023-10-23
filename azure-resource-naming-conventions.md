---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Azure Resource Naming Conventions

A good name for a resource helps you to quickly identify its type, its associated workload, its environment, and the Azure region where it runs. To do so, names should follow a consistent format—a _naming convention_—that is composed of important information about each resource. The information in the names ideally includes whatever you need to identify specific instances of resources. For example, a public IP address (PIP) for a production SharePoint workload in the West US region might be `pip-sharepoint-prod-westus-001`.

![Diagram that shows the components of an Azure resource name.](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/\_images/ready/resource-naming.png)

_Diagram 1: Components of an Azure resource name._

#### Recommended naming components <a href="#recommended-naming-components" id="recommended-naming-components"></a>

When you construct your naming convention, identify the key pieces of information that you want to capture in a resource name. Different information is relevant for different resource types, and not all established naming components can be used for each resource type. Establish a standard naming convention for your environment that is easy to follow, concise, and useful for recognizing information that's relevant to the deployed resource.

The following list provides examples of naming components that are useful when you construct resource names:

| Naming component                          | Description                                                                                                                                                                                                                                                                                                                                           |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Organization**                          | Top-level name of the organization, normally utilized as the top management group or, in smaller organizations, part of the naming convention. Example: `contoso`                                                                                                                                                                                     |
| **Business unit or department**           | Top-level division of your company that owns the subscription or the workload that the resource belongs to. In smaller organizations, this component might represent a single corporate, top-level organizational element. Examples: `fin`, `mktg`, `product`, `it`, `corp`                                                                           |
| **Resource type**                         | An abbreviation that represents the type of Azure resource or asset. This component is often a prefix or suffix in the name. For more information, see [Recommended abbreviations for Azure resource types](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations). Examples: `rg`, `vm` |
| **Project, application, or service name** | Name of a project, application, or service that the resource is a part of. Examples: `navigator`, `emissions`, `sharepoint`, `hadoop`                                                                                                                                                                                                                 |
| **Environment**                           | The stage of the development lifecycle for the workload that the resource supports. Examples: `prod`, `dev`, `qa`, `stage`, `test`                                                                                                                                                                                                                    |
| **Location**                              | The region or cloud provider where the resource is deployed. Examples: `westus`, `eastus2`, `westeu`, `usva`, `ustx`                                                                                                                                                                                                                                  |
| **VM role**                               | Identifier of the purpose of the VM. Examples: `db` (database), `ws` (web server), `ps` (print server)                                                                                                                                                                                                                                                |
| **Instance**                              | The instance count for a specific resource, to differentiate it from other resources that have the same naming convention and naming components. Examples, `01`, `001`                                                                                                                                                                                |

&#x20;Note

Although virtual machine (VM) names in Azure can be longer than the allowed NetBIOS name of the VM, we recommend that you keep them consistent. For more information and for other restrictions, see [Computer names](https://learn.microsoft.com/en-us/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names).

### Naming considerations <a href="#naming-considerations" id="naming-considerations"></a>

In addition to defining the naming components, you must also consider the order in which the naming components are listed and what type of delimiters (if any) should appear between components. Also take into account the different naming rules that are associated with resources types.

#### Scope <a href="#scope" id="scope"></a>

All Azure resource types have a scope that defines the level of that resource. Also, A resource must have a unique name within its scope.

For example, a virtual network has the scope of a resource group, which means that there can be only one network named `vnet-prod-westus-001` in a specific resource group. Other resource groups can also have virtual networks named `vnet-prod-westus-001`, but each resource group can have only one with that name. Subnets are scoped to virtual networks, so each subnet within a virtual network must have a distinct name.

Some resource names have a global scope, such as a name for a Platform as a Service (PaaS) that has a public endpoint or a virtual machine DNS label. A resource in a global scope must have a name that's unique across the entire Azure platform.

![Diagram that shows the scope levels for Azure resource names.](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/\_images/ready/resource-naming-scope.png)

_Diagram 2: Scope levels for Azure resource names._

#### Azure naming rules <a href="#azure-naming-rules" id="azure-naming-rules"></a>

Azure naming rules vary depending on the resource type. When you define a naming convention, it's important to understand Azure naming rules for the resource type to avoid confusion and delay deployments.

For example, resource names have length limits. We recommend that you keep the length of naming components short to prevent exceeding resource name length limits.

&#x20;Note

Balancing the context of a name with its scope and length limit is important when you develop your naming conventions. For more information, see [Naming rules and restrictions for Azure resources](https://learn.microsoft.com/en-us/azure/azure-resource-manager/management/resource-name-rules).

When you construct your naming convention, identify the key pieces of information that you want to reflect in a resource name. Different information is relevant for different resource types. The following list provides examples of information that are useful when you construct resource names.

You can abbreviate resource names and naming components as a strategy to reduce the length and complexity of resource names. Shortening names can be useful for any of the naming components, but it's especially important to help you keep resource names within name length limits. For example, a VM name in Azure can be longer than the OS naming restrictions. Keeping Azure VM names shorter than the naming restrictions of the OS helps create consistency, improve communication when discussing resources, and reduce confusion when you're working in the Azure portal while being signed in to the VM itself.

| Naming component                | Description                                                                                                                                                                                                                                                                                                                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Resource type**               | <p>An abbreviation that represents the type of Azure resource or asset. This component is often used as a prefix or suffix in the name. For more information, see <a href="https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations">Recommended abbreviations for Azure resource types</a>.<br>Examples: <code>rg</code>, <code>vm</code></p> |
| **Business unit**               | <p>Top-level division of your company that owns the subscription or workload the resource belongs to. In smaller organizations, this component might represent a single corporate top-level organizational element.<br>Examples: <code>fin</code>, <code>mktg</code>, <code>product</code>, <code>it</code>, <code>corp</code></p>                                                                       |
| **Application or service name** | <p>Name of the application, workload, or service that the resource is a part of.<br>Examples: <code>navigator</code>, <code>emissions</code>, <code>sharepoint</code>, <code>hadoop</code></p>                                                                                                                                                                                                           |
| **Subscription purpose**        | <p>Summary description of the purpose of the subscription that contains the resource. Often broken down by environment or specific workloads.<br>Examples: <code>prod</code>, <code>shared</code>, <code>client</code></p>                                                                                                                                                                               |
| **Environment**                 | <p>The stage of the development lifecycle for the workload that the resource supports.<br>Examples: <code>prod</code>, <code>dev</code>, <code>qa</code>, <code>stage</code>, <code>test</code></p>                                                                                                                                                                                                      |
| **Region**                      | <p>The Azure region where the resource is deployed.<br>Examples: <code>westus</code>, <code>eastus2</code>, <code>westeu</code>, <code>usva</code>, <code>ustx</code></p>                                                                                                                                                                                                                                |

&#x20;Note

When you're ready to name your resources and assets, review [Recommended abbreviations for Azure resource types](https://learn.microsoft.com/en-us/azure/cloud-adoption-framework/ready/azure-best-practices/resource-abbreviations).

The following section provides example names for common Azure resource types in an enterprise cloud deployment.

&#x20;Note

Some of these example names use a three-digit padding scheme (`###`), such as `mktg-prod-001`.

Padding improves readability and sorting of assets when those assets are managed in a configuration management database (CMDB), IT Asset Management tool, or traditional accounting tools. When the deployed asset is managed centrally as part of a larger inventory or portfolio of IT assets, the padding approach aligns with interfaces those systems use to manage inventory naming.

Unfortunately, the traditional asset padding approach can prove problematic in infrastructure-as-code approaches that might iterate through assets based on a non-padded number. This approach is common during deployment or automated configuration management tasks. Those scripts would have to routinely strip the padding and convert the padded number to a real number, which slows script development and run time.

Choose an approach that's suitable for your organization. The padding shown here illustrates the importance of using a consistent approach to inventory numbering, rather than showing which approach is superior. Before choosing a numbering scheme, with or without padding, evaluate what will affect long-term operations more: CMDB and asset management solutions or code-based inventory management. Then, consistently follow the padding option that best fits your operational needs.

The following section provides some example names for common Azure resource types in an enterprise cloud deployment. For more examples, see the [Azure Naming Tool](https://github.com/mspnp/AzureNamingTool) and the [Naming and tagging tracking template](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/ready/naming-and-tagging-conventions-tracking-template.xlsx).

&#x20;Note

The following examples are intended to provide visualization of a naming convention, but actual conventions vary by organization.

#### Example names: General <a href="#example-names-general" id="example-names-general"></a>

| Asset type                          | Scope                                      | Format and examples                                                                                                                                                                                                                                                         |
| ----------------------------------- | ------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Management group**                | <p>Business unit and/or<br>environment</p> | <p><em>mg-&#x3C;business unit>[-&#x3C;environment>]</em><br><br></p><ul><li><code>mg-mktg</code></li></ul><ul><li><code>mg-hr</code></li></ul><ul><li><code>mg-corp-prod</code></li></ul><ul><li><code>mg-fin-client</code></li></ul>                                       |
| **Subscription**                    | Account / enterprise agreement             | <p><em>&#x3C;business unit>-&#x3C;subscription purpose>-&#x3C;###></em><br><br></p><ul><li><code>mktg-prod-001</code></li></ul><ul><li><code>corp-shared-001</code></li></ul><ul><li><code>fin-client-001</code></li></ul>                                                  |
| **Resource group**                  | Subscription                               | <p><em>rg-&#x3C;app or service name>-&#x3C;subscription purpose>-&#x3C;###></em><br><br></p><ul><li><code>rg-mktgsharepoint-prod-001</code></li></ul><ul><li><code>rg-acctlookupsvc-shared-001</code></li></ul><ul><li><code>rg-ad-dir-services-shared-001</code></li></ul> |
| **API management service instance** | Global                                     | <p><em>apim-&#x3C;app or service name></em><br><br><code>apim-navigator-prod</code></p>                                                                                                                                                                                     |
| **Managed identity**                | Resource group                             | <p><em>id-&#x3C;app or service name>-&#x3C;environment>-&#x3C;region name>-&#x3C;###></em><br><br></p><ul><li><code>id-appcn-keda-prod-eastus2-001</code></li></ul>                                                                                                         |

#### Example names: Networking <a href="#example-names-networking" id="example-names-networking"></a>

| Asset type                       | Scope           | Format and examples                                                                                                                                                                                                                                                 |
| -------------------------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Virtual network**              | Resource group  | <p><em>vnet-&#x3C;subscription purpose>-&#x3C;region>-&#x3C;###></em><br><br></p><ul><li><code>vnet-shared-eastus2-001</code></li></ul><ul><li><code>vnet-prod-westus-001</code></li></ul><ul><li><code>vnet-client-eastus2-001</code></li></ul>                    |
| **Subnet**                       | Virtual network | <p><em>snet-&#x3C;subscription purpose>-&#x3C;region>-&#x3C;###></em><br><br></p><ul><li><code>snet-shared-eastus2-001</code></li></ul><ul><li><code>snet-prod-westus-001</code></li></ul><ul><li><code>snet-client-eastus2-001</code></li></ul>                    |
| **Network interface (NIC)**      | Resource group  | <p><em>nic-&#x3C;##>-&#x3C;vm name>-&#x3C;subscription purpose>-&#x3C;###></em><br><br></p><ul><li><code>nic-01-dc1-shared-001</code></li></ul><ul><li><code>nic-02-vmhadoop1-prod-001</code></li></ul><ul><li><code>nic-02-vmtest1-client-001</code></li></ul>     |
| **Public IP address**            | Resource group  | <p><em>pip-&#x3C;vm name or app name>-&#x3C;environment>-&#x3C;region>-&#x3C;###></em><br><br></p><ul><li><code>pip-dc1-shared-eastus2-001</code></li></ul><ul><li><code>pip-hadoop-prod-westus-001</code></li></ul>                                                |
| **Load balancer**                | Resource group  | <p><em>lb-&#x3C;app name or role>-&#x3C;environment>-&#x3C;###></em><br><br></p><ul><li><code>lb-navigator-prod-001</code></li></ul><ul><li><code>lb-sharepoint-dev-001</code></li></ul>                                                                            |
| **Network security group (NSG)** | Subnet or NIC   | <p><em>nsg-&#x3C;policy name or app name>-&#x3C;###></em><br><br></p><ul><li><code>nsg-weballow-001</code></li></ul><ul><li><code>nsg-rdpallow-001</code></li></ul><ul><li><code>nsg-sqlallow-001</code></li></ul><ul><li><code>nsg-dnsblocked-001</code></li></ul> |
| **Local network gateway**        | Virtual gateway | <p><em>lgw-&#x3C;subscription purpose>-&#x3C;region>-&#x3C;###></em><br><br></p><ul><li><code>lgw-shared-eastus2-001</code></li></ul><ul><li><code>lgw-prod-westus-001</code></li></ul><ul><li><code>lgw-client-eastus2-001</code></li></ul>                        |
| **Virtual network gateway**      | Virtual network | <p><em>vgw-&#x3C;subscription purpose>-&#x3C;region>-&#x3C;###></em><br><br></p><ul><li><code>vgw-shared-eastus2-001</code></li></ul><ul><li><code>vgw-prod-westus-001</code></li></ul><ul><li><code>vgw-client-eastus2-001</code></li></ul>                        |
| **Site-to-Site connection**      | Resource group  | <p><em>cn-&#x3C;local gateway name>-to-&#x3C;virtual gateway name></em><br><br></p><ul><li><code>cn-lgw-shared-eastus2-001-to-vgw-shared-eastus2-001</code></li></ul><ul><li><code>cn-lgw-shared-eastus2-001-to-vgw-shared-westus-001</code></li></ul>              |
| **VPN connection**               | Resource group  | <p><em>cn-&#x3C;subscription1 purpose>>-&#x3C;region1>-to-&#x3C;subscription2 purpose>>-&#x3C;region2>-</em><br><br></p><ul><li><code>cn-shared-eastus2-to-shared-westus</code></li></ul><ul><li><code>cn-prod-eastus2-to-prod-westus</code></li></ul>              |
| **Route table**                  | Resource group  | <p><em>route-&#x3C;route table name></em><br><br></p><ul><li><code>route-navigator</code></li></ul><ul><li><code>route-sharepoint</code></li></ul>                                                                                                                  |
| **DNS label**                    | Global          | <p><em>&#x3C;DNS A record for VM>.&#x3C;region>.cloudapp.azure.com</em><br><br></p><ul><li><code>dc1.westus.cloudapp.azure.com</code></li></ul><ul><li><code>web1.eastus2.cloudapp.azure.com</code></li></ul>                                                       |

#### Example names: Compute and Web <a href="#example-names-compute-and-web" id="example-names-compute-and-web"></a>

| Asset type          | Scope          | Format and examples                                                                                                                                                                                                                                            |
| ------------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Virtual machine** | Resource group | <p><em>vm-&#x3C;vm role>-&#x3C;environment>-&#x3C;###></em><br><br></p><ul><li><code>vm-sql-test-001</code></li></ul><ul><li><code>vm-hadoop-prod-001</code></li></ul>                                                                                         |
| **Web app**         | Global         | <p><em>app-&#x3C;project, app or service>-&#x3C;environment>-&#x3C;###>.azurewebsites.net</em><br><br></p><ul><li><code>app-navigator-prod-001.azurewebsites.net</code></li></ul><ul><li><code>app-accountlookup-dev-001.azurewebsites.net</code></li></ul>    |
| **Function app**    | Global         | <p><em>func-&#x3C;project, app or service>-&#x3C;environment>-&#x3C;###>.azurewebsites.net</em><br><br></p><ul><li><code>func-navigator-prod-001.azurewebsites.net</code></li></ul><ul><li><code>func-accountlookup-dev-001.azurewebsites.net</code></li></ul> |

#### Example names: Databases <a href="#example-names-databases" id="example-names-databases"></a>

| Asset type                         | Scope            | Format and examples                                                                                                                                                                     |
| ---------------------------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Azure SQL database**             | Azure SQL Server | <p><em>sqldb-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>sqldb-users-prod</code></li></ul><ul><li><code>sqldb-users-dev</code></li></ul>            |
| **Azure Cosmos DB database**       | Global           | <p><em>cosmos-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>cosmos-navigator-prod</code></li></ul><ul><li><code>cosmos-emissions-dev</code></li></ul> |
| **Azure Cache for Redis instance** | Global           | <p><em>redis-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>redis-navigator-prod</code></li></ul><ul><li><code>redis-emissions-dev</code></li></ul>    |

#### Example names: Storage <a href="#example-names-storage" id="example-names-storage"></a>

| Asset type                        | Scope  | Format and examples                                                                                                                                                            |
| --------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Storage account (general use)** | Global | <p><em>st&#x3C;project, app or service>&#x3C;###></em><br><br></p><ul><li><code>stnavigatordata001</code></li></ul><ul><li><code>stemissionsoutput001</code></li></ul>         |
| **Azure StorSimple**              | Global | <p><em>ssimp&#x3C;project, app or service>&#x3C;environment></em><br><br></p><ul><li><code>ssimpnavigatorprod</code></li></ul><ul><li><code>ssimpemissionsdev</code></li></ul> |
| **Azure Container Registry**      | Global | <p><em>cr&#x3C;project, app or service>&#x3C;environment>&#x3C;###></em><br><br></p><ul><li><code>crnavigatorprod001</code></li></ul>                                          |

#### Example names: AI and machine learning <a href="#example-names-ai-and-machine-learning" id="example-names-ai-and-machine-learning"></a>

| Asset type                           | Scope          | Format and examples                                                                                                                                                               |
| ------------------------------------ | -------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Azure Cognitive Search**           | Global         | <p><em>srch-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>srch-navigator-prod</code></li></ul><ul><li><code>srch-emissions-dev</code></li></ul> |
| **Azure Cognitive Services**         | Resource group | <p><em>cog-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>cog-navigator-prod</code></li></ul><ul><li><code>cog-emissions-dev</code></li></ul>    |
| **Azure Machine Learning workspace** | Resource group | <p><em>mlw-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>mlw-navigator-prod</code></li></ul><ul><li><code>mlw-emissions-dev</code></li></ul>    |

#### Example names: Analytics and IoT <a href="#example-names-analytics-and-iot" id="example-names-analytics-and-iot"></a>

| Asset type                    | Scope          | Format and examples                                                                                                                                                            |
| ----------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Azure Analysis Services**   | Global         | <p><em>as&#x3C;app name>&#x3C;environment></em><br><br></p><ul><li><code>asnavigatorprod</code></li></ul><ul><li><code>asemissionsdev</code></li></ul>                         |
| **Azure Data Factory**        | Global         | <p><em>adf-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>adf-navigator-prod</code></li></ul><ul><li><code>adf-emissions-dev</code></li></ul> |
| **Azure Stream Analytics**    | Resource group | <p><em>asa-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>asa-navigator-prod</code></li></ul><ul><li><code>asa-emissions-dev</code></li></ul> |
| **Data Lake Storage account** | Global         | <p><em>dls&#x3C;project, app or service>&#x3C;environment></em><br><br></p><ul><li><code>dlsnavigatorprod</code></li></ul><ul><li><code>dlsemissionsdev</code></li></ul>       |
| **IoT hub**                   | Global         | <p><em>iot-&#x3C;project, app or service>-&#x3C;environment></em><br><br></p><ul><li><code>iot-navigator-prod</code></li></ul><ul><li><code>iot-emissions-dev</code></li></ul> |

#### Example names: Integration <a href="#example-names-integration" id="example-names-integration"></a>

| Asset type            | Scope       | Format and Examples                                                                                                                                                                                                                              |
| --------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Service Bus**       | Global      | <p><em>sb-&#x3C;project, app or service>-&#x3C;environment>.servicebus.windows.net</em><br><br></p><ul><li><code>sb-navigator-prod.servicebus.windows.net</code></li></ul><ul><li><code>sb-emissions-dev.servicebus.windows.net</code></li></ul> |
| **Service Bus queue** | Service Bus | <p><em>sbq-&#x3C;query descriptor></em><br><br></p><ul><li><code>sbq-messagequery</code></li></ul>                                                                                                                                               |
| **Service Bus topic** | Service Bus | <p><em>sbt-&#x3C;query descriptor></em><br><br></p><ul><li><code>sbt-messagequery</code></li></ul>                                                                                                                                               |
