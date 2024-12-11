---
title: Getting Started with Property Thumbnail
---
# Getting Started with Property Thumbnail

The Thumbnail is a custom field in the Property Management system.

It is used to store the URL of an image that represents a property.

This field is not required, meaning it can be left empty if no thumbnail is available.

# Thumbnail Field Definition

The Thumbnail field does not track feed history, history, or trending data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Thumbnail__c.field-meta.xml" line="1">

---

For example, in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Thumbnail__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Thumbnail__c.field-meta.xml)</SwmPath>, the Thumbnail field is defined as a URL type custom field.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Thumbnail__c</fullName>
    <externalId>false</externalId>
    <label>Thumbnail</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Url</type>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/propertyTile.js" line="1">

---

# Using the Thumbnail Field

The <SwmToken path="force-app/main/default/objects/Property__c/fields/Thumbnail__c.field-meta.xml" pos="5:4:4" line-data="    &lt;label&gt;Thumbnail&lt;/label&gt;">`Thumbnail`</SwmToken> field is a custom field in the Property Management system used to store the URL of an image representing a property. This field is not required and can be left empty if no thumbnail is available. The <SwmToken path="force-app/main/default/objects/Property__c/fields/Thumbnail__c.field-meta.xml" pos="5:4:4" line-data="    &lt;label&gt;Thumbnail&lt;/label&gt;">`Thumbnail`</SwmToken> field does not track feed history, history, or trending data.

```javascript
import { LightningElement, api } from 'lwc';
import FORM_FACTOR from '@salesforce/client/formFactor';
import { NavigationMixin } from 'lightning/navigation';

export default class PropertyTile extends NavigationMixin(LightningElement) {
    @api property;
    formFactor = FORM_FACTOR;

    handlePropertySelected() {
        if (FORM_FACTOR === 'Small') {
            // In Phones, navigate to property record page directly
            this[NavigationMixin.Navigate]({
                type: 'standard__recordPage',
                attributes: {
                    recordId: this.property.Id,
                    objectApiName: 'Property__c',
                    actionName: 'view'
                }
            });
        } else {
            // In other devices, send message to other cmps on the page
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
