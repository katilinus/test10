# BBVA - test playbook




**Enabled:** True

**Version:** 0

**Type:** Playbook

**Priority:** 2

**Playbook Simulator:** False


### Playbook Trigger
**Trigger Type:** Custom Trigger

**Conditions Operator:** And

##### Conditions
|Key|Operator|Value|
|---|--------|-----|
|asd|Equals|123|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|My Tools_Convert String to JSON_1|Convert a string representing JSON to JSON output. Entities are not used.|My Tools|Convert String to JSON|
|Enrichment_Enrich Entity From JSON_1|The action extracts fields from a json file and adds them to the entity fields|Enrichment|Enrich Entity From JSON|
|Siemplify_Case Comment_1|Add a comment to the case the current alert has been grouped to|Siemplify|Case Comment|

