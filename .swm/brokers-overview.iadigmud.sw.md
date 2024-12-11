---
title: Brokers Overview
---
## Fields

# Brokers Overview

Brokers are custom objects defined in the application to represent real estate brokers. They are used to store and manage information about real estate brokers within the application.

## Compact Layout

The `Broker__c` object includes various fields such as <SwmToken path="force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" pos="4:4:4" line-data="    &lt;fields&gt;Name&lt;/fields&gt;">`Name`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" pos="5:4:4" line-data="    &lt;fields&gt;Title__c&lt;/fields&gt;">`Title__c`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" pos="6:4:4" line-data="    &lt;fields&gt;Phone__c&lt;/fields&gt;">`Phone__c`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" pos="7:4:4" line-data="    &lt;fields&gt;Mobile_Phone__c&lt;/fields&gt;">`Mobile_Phone__c`</SwmToken>, and <SwmToken path="force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" pos="8:4:4" line-data="    &lt;fields&gt;Email__c&lt;/fields&gt;">`Email__c`</SwmToken>, which are used to store relevant information about brokers.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml" line="1">

---

The object has a compact layout defined in <SwmPath>[force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml](force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml)</SwmPath>, which specifies the fields to be displayed in a compact view.

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

<SwmSnippet path="/force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" line="3">

---

## Action Overrides

Additionally, the `Broker__c` object includes action overrides for standard actions like <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="4:4:4" line-data="        &lt;actionName&gt;Accept&lt;/actionName&gt;">`Accept`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="8:4:4" line-data="        &lt;actionName&gt;CancelEdit&lt;/actionName&gt;">`CancelEdit`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="12:4:4" line-data="        &lt;actionName&gt;Clone&lt;/actionName&gt;">`Clone`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="16:4:4" line-data="        &lt;actionName&gt;Delete&lt;/actionName&gt;">`Delete`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="20:4:4" line-data="        &lt;actionName&gt;Edit&lt;/actionName&gt;">`Edit`</SwmToken>, `List`, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="28:4:4" line-data="        &lt;actionName&gt;New&lt;/actionName&gt;">`New`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="32:4:4" line-data="        &lt;actionName&gt;SaveEdit&lt;/actionName&gt;">`SaveEdit`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="36:4:4" line-data="        &lt;actionName&gt;Tab&lt;/actionName&gt;">`Tab`</SwmToken>, and <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="40:4:4" line-data="        &lt;actionName&gt;View&lt;/actionName&gt;">`View`</SwmToken>.

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

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" line="1">

---

## External ID

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken> field is marked as an external ID and is used to uniquely identify brokers.

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

<SwmSnippet path="/force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" line="47">

---

## Configuration

The object is configured to allow bulk API operations, enable reports, search, sharing, and streaming API.

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

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
