---
title: Getting Started with Property Objects
---
# Main Object File

# Introduction to Property Objects

Property objects in the Dreamhouse Lightning Web Components Sample Application represent real estate properties within the Salesforce platform. These objects are custom Salesforce objects defined in XML files and include various metadata configurations.

<SwmSnippet path="/force-app/main/default/objects/Property__c/Property__c.object-meta.xml" line="1">

---

The primary object file, <SwmPath>[force-app/main/default/objects/Property__c/Property__c.object-meta.xml](force-app/main/default/objects/Property__c/Property__c.object-meta.xml)</SwmPath>, contains essential definitions for action overrides, enabling features such as activities, bulk API, feeds, history, and reports. It also specifies the deployment status, sharing model, and visibility settings.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomObject xmlns="http://soap.sforce.com/2006/04/metadata">
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
```

---

</SwmSnippet>

# Fields and List Views

# Compact Layout and Name Field

Additionally, the <SwmPath>[force-app/main/default/objects/Property__c/Property__c.object-meta.xml](force-app/main/default/objects/Property__c/Property__c.object-meta.xml)</SwmPath> file includes a compact layout assignment and a name field configuration. The name field is labeled 'Property Name' and is of type 'Text'.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" line="1">

---

The Properties directory also contains subdirectories for fields and list views. The fields subdirectory includes XML files defining various fields such as `Record_Link__c`, <SwmToken path="force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Description__c&lt;/fullName&gt;">`Description__c`</SwmToken>, `Date_Contracted__c`, and many others. Each field file specifies the field's metadata, including its label, type, and other properties.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Description__c</fullName>
    <externalId>false</externalId>
    <label>Description</label>
    <length>500</length>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>LongTextArea</type>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
