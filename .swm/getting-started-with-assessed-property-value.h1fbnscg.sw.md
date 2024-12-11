---
title: Getting Started with Assessed Property Value
---
# Getting Started with Assessed Property Value

Assessed Value refers to the monetary value assigned to a property for the purposes of taxation.

## Field Type and Precision

It is represented as a custom field in the Property object, specifically defined in the <SwmPath>[force-app/main/default/objects/Property__c/fields/Assessed_Value__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Assessed_Value__c.field-meta.xml)</SwmPath> file.

## Optional Field

The field is of type Currency, with a precision of 18 and a scale of 0, indicating it can store large monetary values without decimal places.

## Usage Example

This field is not required, meaning it can be left empty when creating or updating a property record.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Assessed_Value__c.field-meta.xml" line="1">

---

An example of where Assessed Value is used can be found in the Property object.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Assessed_Value__c</fullName>
    <externalId>false</externalId>
    <label>Assessed Value</label>
    <precision>18</precision>
    <required>false</required>
    <scale>0</scale>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Currency</type>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

# Assessed Value Endpoints

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve the details of a property, including its assessed value. This function is part of the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="2:14:16" line-data="import { getRecord, getFieldValue } from &#39;lightning/uiRecordApi&#39;;">`lightning/uiRecordApi`</SwmToken> module and is wired to the component to fetch data based on the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="26:1:1" line-data="        recordId: &#39;$propertyId&#39;,">`recordId`</SwmToken>.

```javascript
    @wire(getRecord, {
        recordId: '$propertyId',
        fields: [NAME_FIELD, PICTURE_FIELD]
    })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

In the `propertySummary` component, the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is wired to fetch the property details, including the <SwmToken path="force-app/main/default/objects/Property__c/fields/Assessed_Value__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Assessed_Value__c&lt;/fullName&gt;">`Assessed_Value__c`</SwmToken> field, which represents the monetary value assigned to the property for taxation purposes.

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
