---
title: Basic Concepts of Property Address
---
# Basic Concepts of Property Address

The Address field in Property Management refers to the physical location of a property. It is a custom field defined in the Property object.

This field is labeled as 'Address' and is of type 'Text', allowing for a maximum length of 100 characters.

## Field Characteristics

The Address field is not a required field, meaning it can be left empty when creating or updating a property record.

## Optional Field

The Address field is a custom field in the Property object, designed to store the physical location of a property. It is a text field with a maximum length of 100 characters.

## Usage Example

The Address field is optional, meaning it is not mandatory to fill this field when creating or updating a property record.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Address__c.field-meta.xml" line="1">

---

An example of the Address field definition can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Address__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Address__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Address__c</fullName>
    <externalId>false</externalId>
    <label>Address</label>
    <length>100</length>
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

# Address Endpoints

The Address field can be accessed and manipulated through various endpoints.

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> function is used to retrieve a record from Salesforce based on the provided record ID and fields. This function is wired to the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:14:14" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`propertyId`</SwmToken> and retrieves fields such as <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="12:2:4" line-data="    &#39;Property__c.Address__c&#39;,">`Property__c.Address__c`</SwmToken> and <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="13:2:4" line-data="    &#39;Property__c.City__c&#39;,">`Property__c.City__c`</SwmToken>.

```javascript
    @wire(getRecord, { recordId: '$propertyId', fields })
    wiredRecord({ error, data }) {
        if (data) {
            this.error = undefined;
            const property = data.fields;
            this.address = `${property.Address__c.value}, ${property.City__c.value}`;
            this.markers = [
                {
                    location: {
                        Latitude: property.Location__Latitude__s.value,
                        Longitude: property.Location__Longitude__s.value
                    },
                    title: `${property.Name.value}`,
                    description: `<b>Address</b>: ${property.Address__c.value}`,
                    mapIcon: {
                        path: 'M1472 992v480q0 26-19 45t-45 19h-384v-384h-256v384h-384q-26 0-45-19t-19-45v-480q0-1 .5-3t.5-3l575-474 575 474q1 2 1 6zm223-69l-62 74q-8 9-21 11h-3q-13 0-21-7l-692-577-692 577q-12 8-24 7-13-2-21-11l-62-74q-8-10-7-23.5t11-21.5l719-599q32-26 76-26t76 26l244 204v-195q0-14 9-23t23-9h192q14 0 23 9t9 23v408l219 182q10 8 11 21.5t-7 23.5z',
                        fillColor: '#f28b00',
                        fillOpacity: 1,
                        strokeWeight: 1,
                        scale: 0.02
                    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
