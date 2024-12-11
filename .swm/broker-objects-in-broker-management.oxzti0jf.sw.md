---
title: Broker Objects in Broker Management
---
# What is Broker Objects in Broker Management

Broker Objects are custom objects defined to manage broker-related data within the application.

These objects include various fields such as Broker Id, Name, Title, Phone, Mobile Phone, Email, and Picture.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" line="3">

---

The Broker Object also includes action overrides for standard actions like Accept, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="8:4:4" line-data="        &lt;actionName&gt;CancelEdit&lt;/actionName&gt;">`CancelEdit`</SwmToken>, Clone, Delete, Edit, List, New, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="32:4:4" line-data="        &lt;actionName&gt;SaveEdit&lt;/actionName&gt;">`SaveEdit`</SwmToken>, Tab, and View.

```xml
    <actionOverrides>
        <actionName>Accept</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>CancelEdit</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Clone</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Delete</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Edit</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" line="1">

---

Compact layouts are defined for the Broker Object to display essential fields like Name, Title, Phone, Mobile Phone, and Email in a concise format.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CompactLayout xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Broker_Compact</fullName>
    <fields>Name</fields>
    <fields>Title__c</fields>
    <fields>Phone__c</fields>
    <fields>Mobile_Phone__c</fields>
    <fields>Email__c</fields>
    <label>Broker Compact</label>
</CompactLayout>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" line="47">

---

The Broker Object is configured to enable features such as Bulk API, Reports, Search, Sharing, and Streaming API.

```xml
    <enableBulkApi>true</enableBulkApi>
    <enableFeeds>false</enableFeeds>
    <enableHistory>false</enableHistory>
    <enableReports>true</enableReports>
    <enableSearch>true</enableSearch>
    <enableSharing>true</enableSharing>
    <enableStreamingApi>true</enableStreamingApi>
```

---

</SwmSnippet>

## Fields

# Main Functions

There are several main functions in this folder. Some of them are fields, compact layouts, and list views. We will dive a little into fields and compact layouts.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" line="1">

---

Fields in the Broker Objects are used to store various pieces of information related to brokers. These fields include Broker Id, Name, Title, Phone, Mobile Phone, Email, and Picture. Each field is defined with specific attributes such as type, label, and whether it is required or unique.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Broker_Id__c</fullName>
    <externalId>true</externalId>
    <label>Broker Id</label>
    <precision>18</precision>
    <required>false</required>
    <scale>0</scale>
    <trackTrending>false</trackTrending>
    <type>Number</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken>

# Broker Object Endpoints

Broker Object Endpoints provide access to broker-related data and functionalities.

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record from the Salesforce database. It takes the record ID and the fields to be retrieved as parameters. In the context of Broker Objects, it is used to fetch broker-related data such as Broker Id, Name, Phone, Mobile Phone, and Email.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="28">

---

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="28:3:3" line-data="        return getFieldValue(this.property.data, BROKER_FIELD);">`getFieldValue`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="28:3:3" line-data="        return getFieldValue(this.property.data, BROKER_FIELD);">`getFieldValue`</SwmToken> function is used to extract the value of a specific field from a record. This function is particularly useful when dealing with complex objects where direct access to field values is required. For Broker Objects, it is used to access fields like Name, Phone, and Email from the retrieved broker record.

```javascript
        return getFieldValue(this.property.data, BROKER_FIELD);
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
