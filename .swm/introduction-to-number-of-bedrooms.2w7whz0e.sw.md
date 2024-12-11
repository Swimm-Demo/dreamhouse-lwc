---
title: Introduction to Number of Bedrooms
---
# Introduction to Number of Bedrooms

The number of bedrooms, referred to as 'Beds', is a custom field defined in the Property object. This field indicates the number of bedrooms available in a property.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Beds__c.field-meta.xml" line="1">

---

The Beds field is not a required field and is of type Number with a precision of 2 and a scale of 0.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Beds__c</fullName>
    <externalId>false</externalId>
    <label>Beds</label>
    <precision>2</precision>
    <required>false</required>
    <scale>0</scale>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Number</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/propertyTile.html" line="10">

---

This field is used to display the number of bedrooms in various components, such as `propertyTile` and `propertyListMap`.

```html
                <p>Beds: {property.Beds__c} - Baths: {property.Baths__c}</p>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/propertyTile.html" line="10">

---

In the `propertyTile` component, the number of beds is displayed alongside the number of baths.

```html
                <p>Beds: {property.Beds__c} - Baths: {property.Baths__c}</p>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken>

# Beds APIs

The Beds field can be accessed and manipulated through various APIs.

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve the details of a property, including the number of beds. This function is wired to the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="26:6:6" line-data="        recordId: &#39;$propertyId&#39;,">`propertyId`</SwmToken> and fetches the fields defined in the `FIELDS` constant.

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

The <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="18:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields })">`getRecord`</SwmToken> function is also used in the `propertyLocation` component to fetch the latitude and longitude of a property, which can be used to calculate the distance from the user's current location.

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
