---
title: Getting Started with Property Status
---
# Getting Started with Property Status

The Property Status is a custom field in the Property Management module that indicates the current state of a property.

## Purpose of Property Status

It is implemented as a picklist, allowing users to select from predefined values that represent different stages in the property lifecycle.

## Available Statuses

This field helps in tracking the progress and current condition of properties, facilitating better management and decision-making.

## Example Usage

The available statuses include 'Contracted', 'Pre Market', 'Available', 'Under Agreement', and 'Closed'.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Status__c.field-meta.xml" line="1">

---

An example of how Property Status is defined can be seen in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Status__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Status__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Status__c</fullName>
    <externalId>false</externalId>
    <label>Status</label>
    <required>false</required>
    <trackFeedHistory>true</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Picklist</type>
    <valueSet>
        <restricted>true</restricted>
        <valueSetDefinition>
            <sorted>false</sorted>
            <value>
                <fullName>Contracted</fullName>
                <default>false</default>
                <label>Contracted</label>
            </value>
            <value>
                <fullName>Pre Market</fullName>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

## Status Endpoints

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve a record by its ID. This function is wired to the component to fetch data related to the property, including its status.

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
