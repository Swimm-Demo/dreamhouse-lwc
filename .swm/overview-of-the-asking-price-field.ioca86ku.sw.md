---
title: Overview of the Asking Price Field
---
# What is Asking Price

The asking price refers to the price at which a property is listed for sale. It is a key piece of information in property management systems.

In the context of the repository, the asking price is represented as a custom field within the property management system. This field is labeled as 'Asking Price' and is of type 'Currency'.

The precision of the asking price field is set to 8, meaning it can handle values up to eight decimal places. However, it is not a required field, allowing properties to be listed without specifying an asking price.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Price__c.field-meta.xml" line="1">

---

An example of the asking price field can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Price__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Price__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Price__c</fullName>
    <externalId>false</externalId>
    <label>Asking Price</label>
    <precision>8</precision>
    <required>false</required>
    <scale>0</scale>
    <trackFeedHistory>true</trackFeedHistory>
    <trackHistory>true</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Currency</type>
</CustomField>
```

---

</SwmSnippet>

# Usage in Components

The asking price is utilized in various components within the repository. For instance, the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve the details of a property, including its asking price.

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

This function is wired to the `propertySummary` component to fetch the property data based on the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="26:1:1" line-data="        recordId: &#39;$propertyId&#39;,">`recordId`</SwmToken>.

```javascript
    @wire(getRecord, {
        recordId: '$propertyId',
        fields: [NAME_FIELD, PICTURE_FIELD]
    })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="18">

---

Additionally, the <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="18:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields })">`getRecord`</SwmToken> function is used in the `propertyLocation` component to fetch the latitude and longitude fields of a property, which can include the asking price information.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields })
    wiredProperty({ data, error }) {
        if (data) {
            this.property = data;
            this.calculateDistance();
        } else if (error) {
            this.error = error;
            this.property = undefined;
        }
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
