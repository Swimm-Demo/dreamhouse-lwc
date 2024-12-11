---
title: Getting Started with Property Description
---
# Getting Started with Property Description

The Description field is a custom field in the Property Management module.

It is used to store detailed information about a property.

The field is defined as a LongTextArea, allowing for up to 500 characters.

## Usage

This field is not tracked for history or trending changes.

The Description field is used in various parts of the Property Management module, including layouts, flows, and prompts.

<SwmSnippet path="/force-app/main/default/layouts/Property__c-Property Layout.layout-meta.xml" line="75">

---

For example, the Description field is used in the Property Layout and Property Record Page to display detailed information about properties.

```xml
        <label>Description</label>
```

---

</SwmSnippet>

# Property APIs

## Example Usage

The Description field is used in the Property Layout and Property Record Page to display detailed information about properties.

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`getRecord`</SwmToken>

The Property APIs provide functions to interact with property records and their associated data.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="19">

---

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record by its ID. It is wired to the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="20:1:1" line-data="    property;">`property`</SwmToken> variable in the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="14:6:6" line-data="export default class PropertyCarousel extends LightningElement {">`PropertyCarousel`</SwmToken> component to fetch property details such as address, city, and description.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="22">

---

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to retrieve pictures associated with a property. It is wired to the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="23:1:1" line-data="    wiredPictures(pictures) {">`wiredPictures`</SwmToken> method in the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="14:6:6" line-data="export default class PropertyCarousel extends LightningElement {">`PropertyCarousel`</SwmToken> component to fetch and display property images in a carousel format.

```javascript
    @wire(getPictures, { propertyId: '$recordId' })
    wiredPictures(pictures) {
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
