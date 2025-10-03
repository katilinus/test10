# MISP_TEST_Bharat




**Enabled:** False

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
|1|Equals|1|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|MISP_Create Event_1|Create a new event in MISP.|MISP|Create Event|
|MandiantThreatIntelligence_Enrich Entities_1|Enrich entities using information from Mandiant. Supported entities: Hostname, IP Address, URL, Domain, File Hash, Threat Actor, Vulnerability. Note: only MD5, SHA-1 and SHA-256 are supported.|MandiantThreatIntelligence|Enrich Entities|

