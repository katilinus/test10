# GuardDuty Alert Enrichment
Enrich GuardDuty alerts with VirusTotal, retrying on failure, and block malicious IPs.



**Enabled:** False

**Version:** 0

**Type:** Playbook

**Priority:** 2

**Playbook Simulator:** False


### Playbook Trigger
**Trigger Type:** Product Name

**Conditions Operator:** And

##### Conditions
|Key|Operator|Value|
|---|--------|-----|
||Equals|AWS GuardDuty|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|VirusTotalV3_Copy of Search Entity Graphs_1|Search graphs based on the entities in VirusTotal. Supported entities: IP, URL, Filehash, Hostname, Threat Actor, User. Note: only MD5, SHA-1 and SHA-256 are supported.|VirusTotalV3|Copy of Search Entity Graphs|
|Tools_Attach Playbook to Alert_1|This action can attach a playbook or block to an alert.|Tools|Attach Playbook to Alert|

