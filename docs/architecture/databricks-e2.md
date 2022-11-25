This page is intended to hold work-in-progress information for both the Databricks E2 implementation as well as Databricks-to-E2 migration.

Current Actions (Parallel)
--------------------------

- [ ] Use the Vent jobs and notebooks to collect required resources
- [ ] MWS-specific configuration needs
- [ ] Permissions (be it IAM or Databricks-cluster-permissions)
- [ ] Cluster templates (prepared configurations)
- [ ] Access (network to on-prem, Security Group-based access to other systems, peerings)

- [ ] Figure out a base guideline on workspace creation so we have a base or foundation to work off of
- [ ] Some workspaces might exist to purely limit access or visibility
- [ ] Some workspaces might exist to create a legal boundary
- [ ] Some workspaces might exist because of lax or strict policy differences vs. other workspaces
- [ ] Some workspaces might exist to simply make it easier for users to exist in a less-crowded space

- [ ] GitHub Actions support for Databricks-native resources that are too dynamic or arbitrary for Terraform
- [ ] Dedicated runners so we don't get stuck on access control and shared runner limits

- [ ] Databricks provisioning in a separate repository for non-foundational infrastructure
- [ ] This will need something like a terraform configuration, an atlantis configuration and some CODEOWNERS PR limits

  

Structural

<table width="100%" class="gliffy-macro-table"><tbody><tr><td><table class="gliffy-macro-inner-table"><caption align="bottom"></caption><tbody><tr><td><img style="border: none; width: 540px;" usemap="#gliffy-map-64491073-3913" src="attachments/64489985/64491074.png" alt="" class="gliffy-macro-image"></td></tr></tbody></table></td></tr></tbody></table>

  

Migration types
---------------

  

<table class="confluenceTable"><colgroup><col><col><col><col></colgroup><tbody><tr><th class="confluenceTh"><br></th><th class="confluenceTh">Full</th><th class="confluenceTh">Partial</th><th class="confluenceTh">Structural</th></tr><tr><td colspan="1" class="confluenceTd">MWS Type</td><td colspan="1" class="confluenceTd">Fully managed</td><td colspan="1" class="confluenceTd">Structurally managed</td><td colspan="1" class="confluenceTd">Cannot mix with Full or Partial MWS instances</td></tr><tr><td class="confluenceTd">Users</td><td class="confluenceTd">SCIM and/or SAML</td><td class="confluenceTd">SCIM and/or SAML</td><td class="confluenceTd">SCIM and/or SAML</td></tr><tr><td class="confluenceTd">Groups</td><td class="confluenceTd">Terraform</td><td class="confluenceTd">Terraform</td><td class="confluenceTd">Terraform</td></tr><tr><td colspan="1" class="confluenceTd">Group Memberships</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Mixed</td></tr><tr><td class="confluenceTd">Clusters</td><td class="confluenceTd">Terraform</td><td class="confluenceTd">Terraform</td><td class="confluenceTd">Terraform</td></tr><tr><td colspan="1" class="confluenceTd">Cluster IAM Permissions</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Terraform</td></tr><tr><td colspan="1" class="confluenceTd">Group-Cluster Permissions</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Manual</td></tr><tr><td colspan="1" class="confluenceTd">Jobs</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Mixed</td><td colspan="1" class="confluenceTd">Manual</td></tr><tr><td colspan="1" class="confluenceTd">Notebooks</td><td colspan="1" class="confluenceTd">Terraform</td><td colspan="1" class="confluenceTd">Mixed</td><td colspan="1" class="confluenceTd">Manual</td></tr></tbody></table>
