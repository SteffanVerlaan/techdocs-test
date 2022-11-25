**Databricks E2**

This page is intended to hold work-in-progress information for both the Databricks E2 implementation as well as Databricks-to-E2 migration.

Current Actionz (Parallel)

- Use the Vent jobs and notebooks to collect required resources
  - MWS-specific configuration needs
  - Permissions (be it IAM or Databricks-cluster-permissions)
  - Cluster templates (prepared configurations)
  - Access (network to on-prem, Security Group-based access to other systems, peerings)
- Figure out a base guideline on workspace creation so we have a base or foundation to work off of
  - Some workspaces might exist to purely limit access or visibility
  - Some workspaces might exist to create a legal boundary
  - Some workspaces might exist because of lax or strict policy differences vs. other workspaces
  - Some workspaces might exist to simply make it easier for users to exist in a less-crowded space
- GitHub Actions support for Databricks-native resources that are too dynamic or arbitrary for Terraform
  - Dedicated runners so we don't get stuck on access control and shared runner limits
- Databricks provisioning in a separate repository for non-foundational infrastructure
  - This will need something like a terraform configuration, an atlantis configuration and some CODEOWNERS PR limits

Structural

![](Aspose.Words.9ee030a3-7162-4d11-9d88-aa803d205ae3.001.jpeg)

Migration types


||**Full**|**Partial**|**Structural**|
| :- | - | - | - |
|MWS Type|Fully managed|Structurally managed|Cannot mix with Full or Partial MWS instances|
|Users|SCIM and/or SAML|SCIM and/or SAML|SCIM and/or SAML|
|Groups|Terraform|Terraform|Terraform|
|Group Memberships|Terraform|Terraform|Mixed|
|Clusters|Terraform|Terraform|Terraform|
|Cluster IAM Permissions|Terraform|Terraform|Terraform|
|Group-Cluster Permissions|Terraform|Terraform|Manual|
|Jobs|Terraform|Mixed|Manual|
|Notebooks|Terraform|Mixed|Manual|

