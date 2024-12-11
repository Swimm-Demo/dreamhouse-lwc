---
title: Introduction to Number of Bathrooms
---
# Definition

# Introduction

The number of bathrooms, referred to as 'Baths', is an important attribute in real estate listings. This information is essential for potential buyers or renters as it helps them understand the amenities available in the property.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Baths__c.field-meta.xml" line="1">

---

The Baths field is defined as a custom field in the Property object. It is a numeric field with a precision of 2, indicating that it can store numbers with up to two decimal places. This field is not required, meaning that it can be left empty if the information is not available. It is also not unique, allowing multiple properties to have the same number of bathrooms.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Baths__c</fullName>
    <externalId>false</externalId>
    <label>Baths</label>
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

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="181">

---

# Usage

The Baths field is used in various components to display the number of bathrooms in a property. For example, in the `propertyListMap` component, it is displayed alongside the number of beds.

```javascript
    <p>Beds: ${property.Beds__c} - Baths: ${property.Baths__c}</p>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/propertyTile.html" line="10">

---

# Example in Property Tile

Similarly, in the <SwmToken path="force-app/main/default/lwc/propertyTile/__tests__/propertyTile.test.js" pos="2:9:9" line-data="import PropertyTile from &#39;c/propertyTile&#39;;">`propertyTile`</SwmToken> component, the number of baths is displayed along with the number of beds.

```html
                <p>Beds: {property.Beds__c} - Baths: {property.Baths__c}</p>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/__tests__/propertyTile.test.js" line="42">

---

# Test Example

In the test file for <SwmToken path="force-app/main/default/lwc/propertyTile/__tests__/propertyTile.test.js" pos="2:9:9" line-data="import PropertyTile from &#39;c/propertyTile&#39;;">`propertyTile`</SwmToken>, the Baths field is also referenced to ensure that the component displays the correct number of bathrooms.

```javascript
            `Beds: ${PROPERTY.Beds__c} - Baths: ${PROPERTY.Baths__c}`
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
