---
title: Broker in Property Management
---
# What is Broker in Property Management

The Broker refers to a custom field in the Property object.

It is used to establish a relationship between a property and a broker.

The Broker field is a lookup field, meaning it references another object, specifically the Broker object.

This relationship allows properties to be associated with brokers, facilitating the management of property listings and their respective brokers.

# How Broker is used

The field is not required, meaning it is optional to associate a broker with a property.

The Broker field is used in the Property object to link properties with brokers.

# Example of Broker usage

This linkage helps in managing property listings and their respective brokers efficiently.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Broker__c.field-meta.xml" line="1">

---

The Broker field is defined in the Property object as shown in the following snippet.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Broker__c</fullName>
    <deleteConstraint>SetNull</deleteConstraint>
    <externalId>false</externalId>
    <label>Broker</label>
    <referenceTo>Broker__c</referenceTo>
    <relationshipLabel>Properties</relationshipLabel>
    <relationshipName>Properties</relationshipName>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Lookup</type>
</CustomField>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken>

# Broker APIs

Broker APIs are used to interact with the Broker data in the system.

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record by its ID. In the context of the Broker, it is used to fetch the broker details associated with a property.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is wired to the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="25:1:1" line-data="    property;">`property`</SwmToken> property in the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="19:6:6" line-data="export default class BrokerCard extends NavigationMixin(LightningElement) {">`BrokerCard`</SwmToken> component. This allows the component to automatically fetch and display the broker details when the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:9:9" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`recordId`</SwmToken> is set.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="27">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="27:3:3" line-data="    get brokerId() {">`brokerId`</SwmToken> getter method extracts the broker ID from the fetched property data using the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="28:3:3" line-data="        return getFieldValue(this.property.data, BROKER_FIELD);">`getFieldValue`</SwmToken> function.

```javascript
    get brokerId() {
        return getFieldValue(this.property.data, BROKER_FIELD);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken> method uses the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="32:3:3" line-data="        this[NavigationMixin.Navigate]({">`NavigationMixin`</SwmToken> to navigate to the broker's record page when the user clicks the navigate button.

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
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
