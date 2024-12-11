---
title: Introduction to Tags in Property Management
---
# Introduction to Tags in Property Management

Tags are used to categorize properties in the property management system. They provide a way to label and organize properties based on various attributes or characteristics.

## How to Use Tags

The Tags field is a custom text field with a maximum length of 255 characters. It is not a required field, meaning properties can exist without tags. Additionally, the field does not track feed history, history, or trending data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Tags__c.field-meta.xml" line="1">

---

Tags are defined in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Tags__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Tags__c.field-meta.xml)</SwmPath>. This file contains the metadata for the Tags field, specifying its properties and constraints.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Tags__c</fullName>
    <externalId>false</externalId>
    <label>Tags</label>
    <length>255</length>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="2">

---

## Tags API

The Tags API provides functions to interact with the Tags field. One such function is <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="2:4:4" line-data="import { getRecord } from &#39;lightning/uiRecordApi&#39;;">`getRecord`</SwmToken>, which is used to retrieve a record by its ID. This function is commonly used to fetch property details, including tags, from the database.

```javascript
import { getRecord } from 'lightning/uiRecordApi';
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="10">

---

In the `propertyMap` component, the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="2:4:4" line-data="import { getRecord } from &#39;lightning/uiRecordApi&#39;;">`getRecord`</SwmToken> function is wired to fetch property details based on the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="22:1:1" line-data="    propertyId;">`propertyId`</SwmToken>. This includes fields such as <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="11:2:4" line-data="    &#39;Property__c.Name&#39;,">`Property__c.Name`</SwmToken>, <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="12:2:4" line-data="    &#39;Property__c.Address__c&#39;,">`Property__c.Address__c`</SwmToken>, and <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="13:2:4" line-data="    &#39;Property__c.City__c&#39;,">`Property__c.City__c`</SwmToken>.

```javascript
const fields = [
    'Property__c.Name',
    'Property__c.Address__c',
    'Property__c.City__c',
    'Property__c.Location__Latitude__s',
    'Property__c.Location__Longitude__s'
];
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
