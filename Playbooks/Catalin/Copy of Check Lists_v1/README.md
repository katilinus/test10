# Copy of Check Lists_v1




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
|qwe|Equals|123|


### Involved Steps (Unordered)
|Step Name|Description|Integration|Original Action|
|---------|-----------|-----------|---------------|
|Lists_Is String In Custom List-FirstList|The action checks if a specific string exists in a custom list|Lists|Is String In Custom List|
|Functions_String Functions_1|This action includes basic Pythonic string functions as mentioned below - Lower: Converts the input string to lowercase.Upper: Converts the input string to uppercase (duplicated case in the script).Strip: Removes leading and trailing whitespaces from the input string.Title: Converts the first character of each word in the input string to uppercase.Count: Counts the occurrences of `param_1` in the input string.Replace: Replaces occurrences of `param_1` with `param_2` in the input string.Find: Finds the first occurrence of `param_1` in the input string and returns its index.IsAlpha: Checks if all characters in the input string are alphanumeric.IsDigit: Checks if all characters in the input string are digits.Regex Replace: Performs a regex-based replacement of `param_1` with `param_2` in the input string.JSON Serialize: Converts the input string to a JSON formatted string.Regex: Finds all occurrences of the pattern `param_1` in the input string, joins them using `param_2` (defaulting to ", "), and returns the result.DecodeBase64: Decodes the input string from base64 using `param_1` as the encoding type. Default to utf-8EncodeBase64: Encodes the input string in base64 using `param_1` as the encoding type. Default to utf-8RemoveNewLines: Removes new lines from the input string, replacing them with spaces.Split: Splits the input string using `param_1` (or "," if not provided) and adds the result to the Siemplify result.|Functions|String Functions|
|Lists_Add String to Custom List_1|The action adds a string to a custom list.|Lists|Add String to Custom List|
|Lists_Add String to Custom List_FirstList|The action adds a string to a custom list.|Lists|Add String to Custom List|
|Lists_Add String to Custom SecondList|The action adds a string to a custom list.|Lists|Add String to Custom List|
|Siemplify_Case Comment_1|Add a comment to the case the current alert has been grouped to|Siemplify|Case Comment|
|Lists_Remove String from Custom List_2|The action removes a string from a custom list.|Lists|Remove String from Custom List|

