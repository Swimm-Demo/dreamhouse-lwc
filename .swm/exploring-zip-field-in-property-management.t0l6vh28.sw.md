---
title: Exploring Zip Field in Property Management
---
# Exploring Zip Field in Property Management

The Zip field in Property Management is a custom field defined in the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="11:2:2" line-data="    &#39;Property__c.Name&#39;,">`Property__c`</SwmToken> object.

It is used to store the zip code associated with a property.

The field is of type <SwmToken path="force-app/main/default/objects/Property__c/fields/Zip__c.field-meta.xml" pos="11:4:4" line-data="    &lt;type&gt;Text&lt;/type&gt;">`Text`</SwmToken> and has a length of 10 characters.

It is not a required field, meaning it can be left empty.

Additionally, it does not track feed history, history, or trending data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Zip__c.field-meta.xml" line="1">

---

The Zip field is defined in the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="11:2:2" line-data="    &#39;Property__c.Name&#39;,">`Property__c`</SwmToken> object to store the zip code of a property.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Zip__c</fullName>
    <externalId>false</externalId>
    <label>Zip</label>
    <length>10</length>
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

## <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken>

# Property APIs

Property APIs provide functionalities to interact with property records in the Salesforce database.

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> function is used to retrieve a record from the Salesforce database. It takes the record ID and the fields to be retrieved as parameters. This function is widely used across various components to fetch property details.

```javascript
    @wire(getRecord, { recordId: '$propertyId', fields })
    wiredRecord({ error, data }) {
        if (data) {
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="70">

---

## <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="70:7:7" line-data="            const latitude2 = getFieldValue(this.property, LATITUDE_FIELD);">`getFieldValue`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="70:7:7" line-data="            const latitude2 = getFieldValue(this.property, LATITUDE_FIELD);">`getFieldValue`</SwmToken> function is used to extract the value of a specific field from a record. It is often used in conjunction with <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> to access individual field values from the retrieved record data.

```javascript
            const latitude2 = getFieldValue(this.property, LATITUDE_FIELD);
            const longitude1 = this.location.coords.longitude;
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
