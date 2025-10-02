# DEVO_MITS_CA playbook




**Enabled:** False

**Version:** 0

**Type:** Playbook

**Priority:** 2

**Playbook Simulator:** False


### Playbook Trigger
**Trigger Type:** Custom Trigger

**Conditions Operator:** Or

##### Conditions
|Key|Operator|Value|
|---|--------|-----|
|[Alert.Name]|Equals|SECOPSO365AUTHEXCESSIVEFAILEDLOGINSUSERAUTHALLCUSTOM|
|[Alert.Name]|Equals|SECOPSLOGINFAILCOMBINEDSUCCESSEDCUSTOM|
|[Alert.Name]|Equals|SECOPSLOGINFAILATTEMPTSCUSTOM|
|[Alert.Name]|Equals|SECOPSO365AUTHEXCESSIVEFAILEDLOGINSSINGLESOURCECUSTOM|
|[Alert.Name]|Equals|SECOPSAUTHPASSWORDSPRAYIPCUSTOM|
|[Alert.Name]|Equals|SECOPSAUTHPASSWORDSPRAYHOSTCUSTOM|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|ServiceNow_Create Incident_5|Create a new incident in the ServiceNow system|ServiceNow|Create Incident|
|Siemplify_Instruction_8|Set an instruction for the analyst|Siemplify|Instruction|
|EmailV2_Send Email_6|Send email message. Requires: SMTP configuration|EmailV2|Send Email|
|Siemplify_Instruction_3|Instruction|Siemplify|Instruction|
|Siemplify_Instruction_7|Set an instruction for the analyst|Siemplify|Instruction|
|Devo_Advanced Query_5|Malicious URL clicks |Devo|Advanced Query|
|Siemplify_Attach Playbook to Alert_1|Attach a specific playbook to an alert|Siemplify|Attach Playbook to Alert|
|Siemplify_Create Entity_2|Sourceip|Siemplify|Create Entity|
|Siemplify_Create Or Update Entity Properties_15|Invalid username or password event detected |Siemplify|Create Or Update Entity Properties|
|Siemplify_Assign Case_2|Assign case to specific user or usergroup|Siemplify|Assign Case|
|Siemplify_Is In Custom List_1|Check whether an Entity Identifier is part of a predefined dynamic categorized Custom List|Siemplify|Is In Custom List|
|Siemplify_Instruction_11|Perform RCA|Siemplify|Instruction|
|Siemplify_Create Or Update Entity Properties_12|potentially malicious URL click was detected on the account.|Siemplify|Create Or Update Entity Properties|
|Utility_Extract Events as CSV_1||Utility|Extract Events as CSV|
|Devo_Advanced Query_6|LINQ Query to find Invalid username or password event for the account |Devo|Advanced Query|
|EmailV2_Send Email_5|Send email message. Requires: SMTP configuration|EmailV2|Send Email|
|SourceIp risk behavior activity detect |Risk behavior activity detected for Source account|Siemplify|Create Or Update Entity Properties|
|Siemplify_Close Case_1|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|Siemplify_Assign Case_1|Assign case to specific user or usergroup|Siemplify|Assign Case|
|Invalid username or password event detected |Invalid username or password event detected |Siemplify|Create Or Update Entity Properties|
|ServiceNow_Create Incident_3|Create a new incident in the ServiceNow system|ServiceNow|Create Incident|
|Siemplify_Change Case Stage_8|Change case stage to Acknowledgement|Siemplify|Change Case Stage|
|Siemplify_Instruction_14|Set an instruction for the analyst|Siemplify|Instruction|
|Impossible travel alert|Impossible travel alert|Devo|Advanced Query|
|Siemplify_Instruction_2|Provide the list of block IPs|Siemplify|Instruction|
|Siemplify_Create Or Update Entity Properties_1|Detected successful login event on the account.|Siemplify|Create Or Update Entity Properties|
|Siemplify_Create Or Update Entity Properties_2|No successful login event detected on the account.|Siemplify|Create Or Update Entity Properties|
|EmailV2_Send Email_2|Send email message. Requires: SMTP configuration|EmailV2|Send Email|
|ServiceNow_Create Incident_4|Create a new incident in the ServiceNow system|ServiceNow|Create Incident|
|Siemplify_Instruction_6|Discuss with Lead and drop mail to SRT and SET for tunning. |Siemplify|Instruction|
|Devo_Advanced Query_4| Two factor authentication not configured on the account   |Devo|Advanced Query|
|Behavior signal detection for Source account activity|Behavior signal detection for Source account activity|Devo|Advanced Query|
|LINQ Query to find login success event for the user |LINQ Query to find login success event for the user  |Devo|Advanced Query|
|Siemplify_Instruction_13|Set an instruction for the analyst|Siemplify|Instruction|
| No risk behavior activity for source account| No risk behavior activity for source account|Siemplify|Create Or Update Entity Properties|
|Siemplify_Create Or Update Entity Properties_7| Impossible travel alert detected|Siemplify|Create Or Update Entity Properties|
|Siemplify_Instruction_17|Set an instruction for the analyst|Siemplify|Instruction|
|Siemplify_Create Or Update Entity Properties_11|Two-factor authentication configured on the account.|Siemplify|Create Or Update Entity Properties|
|Siemplify_Instruction_18|Set an instruction for the analyst|Siemplify|Instruction|
|Siemplify_Instruction_10|Perform the containment action |Siemplify|Instruction|
|Siemplify_Change Case Stage_4|Change case stage to Notify|Siemplify|Change Case Stage|
|EmailV2_Send Email_3|Send email message. Requires: SMTP configuration|EmailV2|Send Email|
|Siemplify_Create Or Update Entity Properties_14|No Invalid username or password event|Siemplify|Create Or Update Entity Properties|
|Siemplify_Instruction_9|Initiate a bridge call|Siemplify|Instruction|
|Siemplify_Create Or Update Entity Properties_13|potentially malicious URL click was detected on the account.|Siemplify|Create Or Update Entity Properties|
|ServiceNow_Create Incident_2|Create a new incident in the ServiceNow system|ServiceNow|Create Incident|
|Siemplify_Create Or Update Entity Properties_16|Source IP address is bad reputed|Siemplify|Create Or Update Entity Properties|
|Siemplify_Create Or Update Entity Properties_8|No Impossible travel alert|Siemplify|Create Or Update Entity Properties|
|Tools_Find First Alert_1|The action will return the identifier of the first alert in a given case|Tools|Find First Alert|
|Siemplify_Instruction_16|Involve L2/Lead for further investigation |Siemplify|Instruction|
|Siemplify_Create Or Update Entity Properties_17|Source IP address is not bad reputation.|Siemplify|Create Or Update Entity Properties|
| No Invalid username or password event|No Invalid username or password event|Siemplify|Create Or Update Entity Properties|
|Siemplify_Create Or Update Entity Properties_10|No two-factor authentication on the account.|Siemplify|Create Or Update Entity Properties|
|Siemplify_Assign Case_3|Assign case to specific user or usergroup|Siemplify|Assign Case|
|2LINQ Query to find Invalid username or password event for the account |2.LINQ Query to find Invalid username or password event for the account |Devo|Advanced Query|
|Siemplify_Case Comment_1|Suppressed Alert|Siemplify|Case Comment|
|Siemplify_Change Case Stage_3|Change case stage to Resolution|Siemplify|Change Case Stage|

### Involved Blocks
|Name|Description|
|----|-----------|
|TI - Block TF|An embedded workflow that can receive inputs and return an output.|
