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

# Azure Tagging Strategy

When you apply metadata tags to your cloud resources, include information that couldn't be included in the resource name. For example, include information about the asset. You can use that information to run more sophisticated filtering and reporting on resources. You want these tags to include context about the resource's associated workload or application, operational requirements, and ownership information. IT or business teams use this information to find resources or generate reports about resource usage and billing.

What tags you apply to resources and what tags are required or optional differs among organizations. The following list provides examples of common tags that capture important context and information about a resource. Use this list as a starting point to establish your own tagging conventions.

### Minimum suggested tags <a href="#minimum-suggested-tags" id="minimum-suggested-tags"></a>

The following tags guide implementation and processes in Cloud Adoption Framework methodologies. Many of the best practices in those methodologies demonstrate cloud operations automation and governance based on the following tags.

| Tag Name                  | Description                                                                                                                                                                                                               | Key and example values                                                                                                                                                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Workload name**         | Name of the workload the resource supports.                                                                                                                                                                               | <p><em>WorkloadName</em><br><br></p><ul><li><code>ControlCharts</code></li></ul>                                                                                                                                                                              |
| **Data classification**   | Sensitivity of data hosted by this resource.                                                                                                                                                                              | <p><em>DataClassification</em><br><br></p><ul><li><code>Non-business</code></li></ul><ul><li><code>Public</code></li></ul><ul><li><code>General</code></li></ul><ul><li><code>Confidential</code></li></ul><ul><li><code>Highly confidential</code></li></ul> |
| **Business criticality**  | Business impact of the resource or supported workload.                                                                                                                                                                    | <p><em>Criticality</em><br><br></p><ul><li><code>Low</code></li></ul><ul><li><code>Medium</code></li></ul><ul><li><code>High</code></li></ul><ul><li><code>Business unit-critical</code></li></ul><ul><li><code>Mission-critical</code></li></ul>             |
| **Business unit**         | Top-level division of your company that owns the subscription or workload that the resource belongs to. In smaller organizations, this tag might represent a single corporate or shared top-level organizational element. | <p><em>BusinessUnit</em><br><br></p><ul><li><code>Finance</code></li></ul><ul><li><code>Marketing</code></li></ul><ul><li><code>Product XYZ</code></li></ul><ul><li><code>Corp</code></li></ul><ul><li><code>Shared</code></li></ul>                          |
| **Operations commitment** | Level of operations support provided for this workload or resource.                                                                                                                                                       | <p><em>OpsCommitment</em><br><br></p><ul><li><code>Baseline only</code></li></ul><ul><li><code>Enhanced baseline</code></li></ul><ul><li><code>Platform operations</code></li></ul><ul><li><code>Workload operations</code></li></ul>                         |
| **Operations team**       | Team accountable for day-to-day operations.                                                                                                                                                                               | <p><em>OpsTeam</em><br><br></p><ul><li><code>Central IT</code></li></ul><ul><li><code>Cloud operations</code></li></ul><ul><li><code>ControlCharts team</code></li></ul><ul><li><code>MSP-{Managed Service Provider name}</code></li></ul>                    |

### Other common tagging examples <a href="#other-common-tagging-examples" id="other-common-tagging-examples"></a>

Use the following tags to increase visibility into the usage of Azure resources.

| Tag Name                      | Description                                                                                | Key and example values                                                                                                                                                                                   |
| ----------------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Application name**          | Added granularity, if the workload is subdivided across multiple applications or services. | <p><em>ApplicationName</em><br><br></p><ul><li><code>IssueTrackingSystem</code></li></ul>                                                                                                                |
| **Approver name**             | Person responsible for approving costs related to this resource.                           | <p><em>Approver</em><br><br></p><ul><li><code>chris@contoso.com</code></li></ul>                                                                                                                         |
| **Budget required/approved**  | Money approved for this application, service, or workload.                                 | <p><em>BudgetAmount</em><br><br></p><ul><li><code>$200,000</code></li></ul>                                                                                                                              |
| **Cost center**               | Accounting cost center associated with this resource.                                      | <p><em>CostCenter</em><br><br></p><ul><li><code>55332</code></li></ul>                                                                                                                                   |
| **Disaster recovery**         | Business criticality of the application, workload, or service.                             | <p><em>DR</em><br><br></p><ul><li><code>Mission-critical</code></li></ul><ul><li><code>Critical</code></li></ul><ul><li><code>Essential</code></li></ul>                                                 |
| **End date of the project**   | Date when the application, workload, or service is scheduled for retirement.               | <p><em>EndDate</em><br><br></p><ul><li><code>2023-10-15</code></li></ul>                                                                                                                                 |
| **Environment**               | Deployment environment of the application, workload, or service.                           | <p><em>Env</em><br><br></p><ul><li><code>Prod</code></li></ul><ul><li><code>Dev</code></li></ul><ul><li><code>QA</code></li></ul><ul><li><code>Stage</code></li></ul><ul><li><code>Test</code></li></ul> |
| **Owner name**                | Owner of the application, workload, or service.                                            | <p><em>Owner</em><br><br></p><ul><li><code>jane@contoso.com</code></li></ul>                                                                                                                             |
| **Requester name**            | User who requested the creation of this application.                                       | <p><em>Requester</em><br><br></p><ul><li><code>john@contoso.com</code></li></ul>                                                                                                                         |
| **Service class**             | Service level agreement level of the application, workload, or service.                    | <p><em>ServiceClass</em><br><br></p><ul><li><code>Dev</code></li></ul><ul><li><code>Bronze</code></li></ul><ul><li><code>Silver</code></li></ul><ul><li><code>Gold</code></li></ul>                      |
| **Start date of the project** | Date when the application, workload, or service was first deployed.                        | <p><em>StartDate</em><br><br></p><ul><li><code>2020-10-15</code></li></ul>                                                                                                                               |
