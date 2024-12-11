---
title: Getting Started with Contract Date
---
## Purpose of Date Contracted

# Getting Started with Contract Date

Date Contracted refers to the specific date when a property contract is signed or agreed upon.

## Characteristics of Date Contracted

This field is used to track the date on which the property contract becomes effective.

## Example of Date Contracted

It is a custom field in the Property object and is not required, meaning it can be left empty if the date is not available. The field type is Date, which ensures that only date values can be entered.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Date_Contracted__c.field-meta.xml" line="1">

---

An example of the Date Contracted field can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Date_Contracted__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Date_Contracted__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Date_Contracted__c</fullName>
    <externalId>false</externalId>
    <label>Date Contracted</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Date</type>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

## Retrieving Date Contracted

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve a record by its ID. It is wired to the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="26:6:6" line-data="        recordId: &#39;$propertyId&#39;,">`propertyId`</SwmToken> and fetches fields such as <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Contracted__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Date_Contracted__c&lt;/fullName&gt;">`Date_Contracted__c`</SwmToken>.

```javascript
    @wire(getRecord, {
        recordId: '$propertyId',
        fields: [NAME_FIELD, PICTURE_FIELD]
    })
    property;
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
