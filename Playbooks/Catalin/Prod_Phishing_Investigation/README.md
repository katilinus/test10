# Prod_Phishing_Investigation
Playbook used to enrich emails pulled in via a connector to the suspicious email triage mailbox.

It works with two main reporting mechanisms (MS Report Phishing add-in and Proofpoint's PhishAlarm Analyzer). Entities are submitted for enhancement to VirusTotal, VMRay, Anomali



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
|[Alert.Product]|Equals|Exchange

|
|[Alert.Name]|Equals|Exchange Monitored Mailbox <FM_.SuspiciousEmails@admiralgroup.co.uk>|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|Close_Case_Genuine|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|Send_Mail_Spam|Send spam email template response to all submitters.|Exchange|Send Mail HTML|
|Incident Handling Links|Add links to processes in Confluence on responsive actions and how to perform them. This will appear in the case wall as an insight.|Siemplify|Add General Insight|
|Case Tag-SOC_CASE_TRIAGE|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Save_B64_To_File_Backup_Spam|The action saves a base64 string to a file.  It supports comma separated lists for Filename and Base64 Input.  The optional File Extension parameter is used to add an extension to the output filename.|FileUtilities|Save Base64 to File|
|Email_Parsing_Output|The action receives a json string and returns it as a json result that can be processed by other actions in Chronicle SOAR natively|Tools|Buffer|
|Case_Tag_Genuine|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|UDM_Query_Email_Subject|Return all emails that have the same email subject as the subject in the suspicious email|GoogleChronicle|Execute UDM Query|
|Assign_Case_SOC|Assigned to SOC Triage Analyst.|Siemplify|Assign Case|
|Close_Case_Spam|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|Save_File_Safe_Internal_Sender|The action saves a base64 string to a file.  It supports comma separated lists for Filename and Base64 Input.  The optional File Extension parameter is used to add an extension to the output filename.|FileUtilities|Save Base64 to File|
|Case_Tag_Approved_Internal_Sender|Add tag that is an approved internal sender|Siemplify|Case Tag|
|Parse_EML_file_regex_exclusions|This action will parse an EML or MSG file that has been attached to the case wall and extract entities. Excludes image files from being parsed out as entities.|EmailUtilities|Parse Case Wall Email - Symantec|
|Get_Screenshot_URL_HatchingTriage|Use scan IDs from Hatching triage to return task results (including screenshot url, report url from urlscan.io)|HatchingTriage|Get Screenshot|
|Change_Case_Name_2|Change the case name to be of the email subject only - the goal is that Phish Alarm and MS phishing submissions are combined into the same case where the same email is reported.|Tools|Change Case Name|
|Set_Context_Value_No_Regex_Exclusions|The action sets a key and value in a specific context (alert or case)|Tools|Set Context Value|
|Case_Tag_MS_Addin|Add tag to show that the email was reported using MS addin|Siemplify|Case Tag|
|Send_Mail_Generic_Phishing|Send generic phishing email template response to all submitters.|Exchange|Send Mail HTML|
|Set_Context_Email_Parsing_Regex_Exclusions|The action sets a key and value in a specific context (alert or case)|Tools|Set Context Value|
|Close_Case_Malicious_URL|Malicious URL has been identified|Siemplify|Close Case|
|Get_Case_Data_Spam|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|Close_Case_Malicious_Attachment|Malicious attachment has been identified|Siemplify|Close Case|
|Enrichment_Enrich Entity With Field_1|This enrichment adds a field that will allow for URL_Filter to be passed into a second filter stage.|Enrichment|Enrich Entity With Field|
|Split HTML body|This action will split the sanitized html body by using end email headers as the separator and returning the split string as an array.|Functions|String Functions|
|Approved_Sender_Found_Insight|Add a general insight saying approved entity has been found.|Siemplify|Add General Insight|
|Close_Case_Generic_Phishing|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|Get_Case_Data_Generic_Phishing|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|is_approved_external_sender|Checks if the from email is on the phishing_external_approved_headers custom list.|Lists|Is String In Custom List|
|Send_Mail_Proper_Reporting_Mechanisms|Send email telling submitter to use one of the two authorised methods.|Exchange|Send Mail HTML|
|Set Context Value_EmailHeaderAnalysis_Phish Alarm|Extract email headers from a Phish Alarm reported email and save as a specific global variable that can be used in the playbook view.|Tools|Set Context Value|
|UDM_Query_Email_To|Return all emails to the submitter of the suspicious email|GoogleChronicle|Execute UDM Query|
|Get_Email_Attachments|The actions gets an attachment from the case wall (the result is presented as a Base64). This is the first step to be able to submit the files for analysis to VMRay.|FileUtilities|Get Attachment|
|Case_Priority_High|3 or 4 suspicious entities - assign high case priority|Siemplify|Change Priority|
|Submit_URL_HatchingTriage|Submit URL to Hatching Triage so that analysis can start and the urls can be submitted to URLScan.io private scans. This will return scan IDs that can be used in future steps. Following steps happen at the end of the playbook to give time for the analysis to proceed.|HatchingTriage|Analyse URL|
|MDTI-Test_Enrich Entity_1|Enriches IPs or hostnames using Microsoft's Defender TI data.https://techcommunity.microsoft.com/t5/microsoft-defender-threat/what-s-new-apis-in-microsoft-graph/ba-p/3780350https://learn.microsoft.com/en-us/graph/api/resources/security-api-overview?view=graph-rest-beta#alerts-and-incidents-preview|MDTI-Test|Enrich Entity|
|Send_Mail_Genuine|Send genuine email template response to all submitters.|Exchange|Send Mail HTML|
|Save_File_External_Safe_Sender|The action saves a base64 string to a file.  It supports comma separated lists for Filename and Base64 Input.  The optional File Extension parameter is used to add an extension to the output filename.|FileUtilities|Save Base64 to File|
|Set_Context_Value_Email_Date|Extract identity of the suspicious email receipt date|Tools|Set Context Value|
|Set_Context_Value_Email_From|Extract the sender identity from the submitted email|Tools|Set Context Value|
|Set_Context_Value_Email_Subject|Extract the subject of the submitted email|Tools|Set Context Value|
|Set_Context_Value_Email_To|Extract identity of the suspicious email submitter|Tools|Set Context Value|
|Case-Tag: SUSP_EMAIL_AUTO_CLOSED|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Close_Case_VMRay_Automated_Response|Do not need to investigate automated VMRay responses to manual submissions from the mailbox.|Siemplify|Close Case|
|Case_Priority_Medium|1 or 2 suspicious entity detected - Assign Medium Case priority|Siemplify|Change Priority|
|Send_Mail_Malicious|Send malicious email template response to all submitters.|Exchange|Send Mail HTML|
|Enrichment_Enrich_Entity_Filter_1|This enrichment adds a field that will allow for URL_Filter to be passed into a second filter stage.|Enrichment|Enrich Entity With Field|
|Case_Tag_Incorrect_Submission_Methods|Tag the alert as incorrectly submitted (e.g. manually forwarded, manually added as an attachment and then sent). This branch also acts as a catch all branch for auto replies, manual replies back to submission verdicts and any other edge cases.|Siemplify|Case Tag|
|First_Unique_Email_Submitted|This action checks if the alert is an email that has been reported for the first time. Uniqueness within a case of the suspicious email connector is done on an email subject basis.|Tools|Find First Alert|
|Set Context Value_EmailHeaderAnalysis_Microsoft Phishing Report|Extract email headers from a MS reported email and save as a specific global variable that can be used in the playbook view.|Tools|Set Context Value|
|duplicate alert note|Adds a general entity insight to the case wall that this alert has been caused to a duplicate submission of a suspicious email (regardless of the fact that all submissions are important and welcome).|Siemplify|Add General Insight|
|Send_Mail_Spearphishing|Send spearphishing email template response to all submitters.|Exchange|Send Mail HTML|
|Get_Case_Data_Spearphishing|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|Get_Case_Data_Whalephishing|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|has_approved_header|Checks if the string created in the previous step contains any headers from the phishing_approved_headers custom list.|Lists|Is String In Custom List|
|Get_Context Value_Email_Date|Stores the variable of the email received date from the two submission method branches|Tools|Get Context Value|
|Get_Context_Value_Email_From|Stores the variable of email_from from the two submission method branches|Tools|Get Context Value|
|Get_Context_Value_Email_Subject|Stores the variable of email_subject from the two submission method branches|Tools|Get Context Value|
|Get_Context_Value_Email_To|Stores the variable of email_to from the two submission method branches|Tools|Get Context Value|
|Combine headers|Combine all headers field names into one combined string with headers separated by commas.|TemplateEngine|Render Template|
|Approved_External_Sender_Case_Tag|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Tag_Phishing_Investigation|Add a base case tag that shows this is a phishing investigation.|Siemplify|Case Tag|
|Case_Tag_Malicous_URL|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Case_Tag_Internal_Email|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Get Context Value_EmailHeaderAnalysis|Get variable containing email headers from one of the reporting mechanism branches for use in a playbook view|Tools|Get Context Value|
|Get Attachment_Fallback_Genuine|The actions gets an attachment from the case wall (the result is presented as a Base64)|FileUtilities|Get Attachment|
|Close_Case_Whalephishing|Malicious URL has been identified|Siemplify|Close Case|
|Get_Attachment_Safe_External_Sender|The actions gets an attachment from the case wall (the result is presented as a Base64)|FileUtilities|Get Attachment|
|Close_Case_Safe_External_Sender|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|Case_Tag_VMRay_Automated_Response|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Get_Case_Data_External_Sender|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|NestedHeaderJSONResults|Extract email authenticator headers from the previous step and return them as a json object - to be used in a playbook view|Tools|Buffer|
|Send_Mail_Whalephishing|Send spearphishing email template response to all submitters.|Exchange|Send Mail HTML|
|Case_Tag_Spam|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Case_Tag_Malicious_Attachment|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Approved_External_Sender|Add a general insight configurable message to the case|Siemplify|Add General Insight|
|Case_Tag_Whalephishing|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Set_Context_Email_Date|Extract identity of the suspicious email date|Tools|Set Context Value|
|Set_Context_Value_Email_From|Extract the sender identity from the submitted email|Tools|Set Context Value|
|Set_Context_Value_Email_Subject|Extract the subject of the submitted email|Tools|Set Context Value|
|Set_Context_Value_Email_To|Extract identity of the suspicious email submitter|Tools|Set Context Value|
|Get_Context_Email_Parsing_Output|The action gets a key and value in a specific context (alert or case)|Tools|Get Context Value|
|Change Case Name_1|The action changes the case's name (title)|Tools|Change Case Name|
|Close_Case_Spearphishing|Malicious URL has been identified|Siemplify|Close Case|
|Get_Case_Data_Approved_Sender|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|Case_Tag_Spearphishing|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Get_Attachment_Safe_Internal_Sender|The actions gets an attachment from the case wall (the result is presented as a Base64). This action is used as a backup in case attachments got overwritten due to the local file system being purged on a weekly basis.|FileUtilities|Get Attachment|
|Case_Tag_Generic_Phishing|Add given tag to the case the current alert is grouped to|Siemplify|Case Tag|
|Parse_EML_file_no_regex_exclusions|This action will parse an EML or MSG file that has been attached to the case wall and extract entities. Excludes image files from being parsed out as entities. This does not exclude any images from being parsed out and is used as a backstop if the base parse case wall action fails.|EmailUtilities|Parse Case Wall Email - Symantec|
|Case_Priority_Critical|5 or more suspicious entity detected - Assign Critical Case priority|Siemplify|Change Priority|
|VMRay_Scan Hash|VMRay hash entity enhancement action. Create entity insight only when VMRay finds it to be have a threat indicator higher or equal to 3.|VMRay|Scan Hash|
|VMRay_Scan URL|URL enrichment action - entity insight created if entity was determined to have a threat indicator higher or equal to 3.|VMRay|Scan URL|
|VMRay_Upload File And Get Report|Submit files for analysis in VMRay from the filtered list of email attachments. Timeout value has been set to 10 mins to allow playbook to continue to completion.|VMRay|Upload File And Get Report|
|Get Attachment_Fallback_Spam|The actions gets an attachment from the case wall (the result is presented as a Base64)|FileUtilities|Get Attachment|
|Case_Tag_PhishAlarm|Tag the alert as having used the PhishAlarm reporting mechanism|Siemplify|Case Tag|
|Get_Full_Scan_Details_Urlscanio|Get Scan Full Details by scan ID|UrlScanIo|Get Scan Full Details|
|Get_Case_Data_Genuine|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|
|Save_Base64_to _Local_File|The action saves a base64 string to a file locally on the system. This would then allow for those local files to be submitted to the VMRay sandbox.|FileUtilities|Save Base64 to File|
|Send_Mail_Safe_Sender|Send genuine email template response to all submitters.|Exchange|Send Mail HTML|
|Count All Sus Entities|Count the number of entities from a specific scope without filtering for entity type.|SiemplifyUtilities|Count Entities In Scope_No Entity Type Filtering|
|Save_B64_To_File_Backup_Genuine|The action saves a base64 string to a file.  It supports comma separated lists for Filename and Base64 Input.  The optional File Extension parameter is used to add an extension to the output filename.|FileUtilities|Save Base64 to File|
|Add_General_Email_Submitter|Add an insight with the identity of the submitter of the email - this to allow for all the submitter emails to be stored within the case data.|Siemplify|Add General Insight|
|is_approved_sender|Checks if the from email is on the phishing_approved_headers custom list.|Lists|Is String In Custom List|
|AnomaliThreatStream_Enrich Entities|Retrieve information about IPs, URLs, hashes or User entities with Email regexes from Siemplify ThreatFuse. If multiple records are found for the same entity, action will enrich using the latest record. Entity insights will only be created if the entities were found to be suspicious by Anomali.|AnomaliThreatStream|Enrich Entities|
|Change Case Stage-Triage|Change case stage to handling|Siemplify|Change Case Stage|
|Sanitize HTML|Given a fragment of HTML, SantizeHTML will parse it according to the HTML5 parsing algorithm and sanitize any disallowed tags or attributes. This algorithm also takes care of things like unclosed and (some) misnested tags.|Functions|SanitizeHTML|
|Send Mail - Legit External Sender|Send an email with HTML template content, Send to field is comma separated. Note: Sender's display name can be configured in the client under the account settings|Exchange|Send Mail HTML|
|Close_Case_Safe_Internal_Sender|Closes the case the current alert has been grouped to|Siemplify|Close Case|
|UDM_Query_Email_From|Searches Google Chronicle for all emails from the sender of the submitted email|GoogleChronicle|Execute UDM Query|
|Dummy Count|Step added here to allow for the else clause to be linked back into the main branch|SiemplifyUtilities|Count Entities In Scope_No Entity Type Filtering|
|Get_Case_Data_Malicious|This action will get all the data from a case and return a JSON result.  The result includes comments, entity information, insights, playbooks that ran, alert information and events.|Tools|Get Case Data|

### Involved Blocks
|Name|Description|
|----|-----------|
|Prod_Analyze_Headers|This block accepts email headers and performs various risk checks to create an aggregate risk score for a suspicious email.|
|Prod_VirusTotal_Enrichment|This block accepts an alert as input and enhances IPs, domains and hashes with TI where available. No entity enhancement is created if none is available in VT. |
|Prod_Domain_Investigation|Enriches URLs, Emails, Domains, and IP addresses with WHOIS information.  Will create domain entities and link to URLs and Emails.  Will set any domain that is less than 180 days old as suspicious.  Checks to see if domains are look a like domains. |
|Prod_Analyze_Headers|This block accepts email headers and performs various risk checks to create an aggregate risk score for a suspicious email.|
|Prod_Body_Analysis|This block will check the body for zero width spaces after creating a json object composed of specific email header elements.|
|Prod_Body_Analysis|This block will check the body for zero width spaces after creating a json object composed of specific email header elements.|
