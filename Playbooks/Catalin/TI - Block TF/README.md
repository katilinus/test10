# TI - Block TF
An embedded workflow that can receive inputs and return an output.



**Enabled:** True

**Version:** 0

**Type:** Block

**Priority:** 2

**Playbook Simulator:** False


##### Input Parameters
|Name|Default Value|
|----|-------------|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|SiemplifyThreatFuse_Enrich Entities_3|Retrieve information about hashes in Enrich Entities_3|SiemplifyThreatFuse|Enrich Entities|
|SiemplifyThreatFuse_Enrich Entities_6|Retrieve information about Domains in Enrich Entities_6|SiemplifyThreatFuse|Enrich Entities|
|SiemplifyThreatFuse_Get Related URLs_1|Retrieve entity related urls based on the associations in Siemplify ThreatFuse.|SiemplifyThreatFuse|Get Related URLs|
|SiemplifyThreatFuse_Enrich Entities_1|Retrieve information about IPs  in Enrich Entities_1|SiemplifyThreatFuse|Enrich Entities|
|TemplateEngine_Render Template_1|This action will render a Jinja2 template using a JSON input.  |TemplateEngine|Render Template|
|SiemplifyThreatFuse_Enrich Entities_5|Retrieve information about IPs, URLs, hashes, email addresses from Siemplify ThreatFuse. If multiple records are found for the same entity, action will enrich using the latest record.|SiemplifyThreatFuse|Enrich Entities|
|SiemplifyThreatFuse_Get Related IPs_1|Retrieve entity related IP addresses based on the associations in Siemplify ThreatFuse.|SiemplifyThreatFuse|Get Related IPs|
|SiemplifyThreatFuse_Get Related Associations_1|Retrieve entity related associations from Siemplify ThreatFuse. Configure the parameters below: choose the association types to return, specify Max Associations To Return. You can also choose to add retrieved associations as entities to the case.|SiemplifyThreatFuse|Get Related Associations|
|SiemplifyThreatFuse_Enrich Entities_4|Retrieve information about URLs on Enrich Entities_4|SiemplifyThreatFuse|Enrich Entities|

