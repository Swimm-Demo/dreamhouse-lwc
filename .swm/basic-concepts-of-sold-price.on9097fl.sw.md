---
title: Basic Concepts of Sold Price
---
# Basic Concepts of Sold Price

Price Sold refers to the final selling price of a property. It is a custom field in the Property Management system.

This field is defined with a precision of 8 and a scale of 0, indicating it is a currency type without decimal places.

The field is not required, meaning it can be left empty if the property has not been sold yet.

Price Sold is used in the Property Management system to record the final selling price of a property.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Price_Sold__c.field-meta.xml" line="1">

---

An example of its definition can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Price_Sold__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Price_Sold__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Price_Sold__c</fullName>
    <externalId>false</externalId>
    <label>Price Sold</label>
    <precision>8</precision>
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

# Retrieving Sold Price Data

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve the details of a property, including the Price Sold field. This function is wired to the component and fetches the record data based on the provided record ID.

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
