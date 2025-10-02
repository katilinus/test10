# Isolate MSDefender Alerts
Isolates devices upon receiving alerts from Microsoft Defender for Endpoints.



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
||Equals|MSDefender for Endpoints|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|Siemplify_Case Comment_1|Add a comment to the case the current alert has been grouped to|Siemplify|Case Comment|
|MicrosoftDefenderATP_martha Create Isolate Machine Task_1|Create Isolate Machine Task|MicrosoftDefenderATP|martha Create Isolate Machine Task|

