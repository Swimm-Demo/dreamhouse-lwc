---
title: Broker Management Overview
---
# Broker Management Overview

Broker Management refers to the handling and organization of broker-related data and functionalities within the application.

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="5:14:14" line-data="import BROKER_FIELD from &#39;@salesforce/schema/Property__c.Broker__c&#39;;">`Broker__c`</SwmToken> object is a custom object that represents brokers, including their details and actions that can be performed on them.

This object includes various action overrides such as Accept, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="8:4:4" line-data="        &lt;actionName&gt;CancelEdit&lt;/actionName&gt;">`CancelEdit`</SwmToken>, Clone, Delete, Edit, List, New, <SwmToken path="force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" pos="32:4:4" line-data="        &lt;actionName&gt;SaveEdit&lt;/actionName&gt;">`SaveEdit`</SwmToken>, Tab, and View, which define the default behaviors for these actions.

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="5:14:14" line-data="import BROKER_FIELD from &#39;@salesforce/schema/Property__c.Broker__c&#39;;">`Broker__c`</SwmToken> object is configured to be deployed, searchable, and shareable, with activities and feeds disabled.

The compact layout for brokers, defined in <SwmPath>[force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml](force-app/main/default/objects/Broker__c/compactLayouts/Broker_Compact.compactLayout-meta.xml)</SwmPath>, specifies the fields to be displayed in a compact view, including Name, Title, Phone, Mobile Phone, and Email.

## Why Broker Management is Used

The `Broker_Id__c` field is a custom field that serves as an external ID for brokers, ensuring each broker has a unique identifier.

## How Broker Management is Implemented

Broker Management is used to manage broker-related data and actions, ensuring that brokers' information is organized and accessible.

## Example of Broker Management Usage

Broker Management is implemented through the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="5:14:14" line-data="import BROKER_FIELD from &#39;@salesforce/schema/Property__c.Broker__c&#39;;">`Broker__c`</SwmToken> custom object, which includes various action overrides and configurations.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml" line="3">

---

Broker Management is used in the <SwmPath>[force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml](force-app/main/default/objects/Broker__c/Broker__c.object-meta.xml)</SwmPath> file.

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

### <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken>

## Broker Management Endpoints

Broker Management Endpoints provide functionalities to interact with broker data.

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record by its ID. In the context of Broker Management, it is used to fetch broker-related data. For example, in the `brokerCard` component, the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is wired to fetch the broker's details using the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:9:9" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`recordId`</SwmToken>.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

### <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken> function is used to navigate to a specific record page. In the `brokerCard` component, this function is triggered by a button click to navigate to the broker's record page.

```javascript
    handleNavigateToRecord() {
        this[NavigationMixin.Navigate]({
            type: 'standard__recordPage',
            attributes: {
                recordId: this.brokerId,
                objectApiName: 'Property__c',
                actionName: 'view'
            }
        });
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
