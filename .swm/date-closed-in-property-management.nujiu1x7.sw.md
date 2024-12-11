---
title: Date Closed in Property Management
---
# Data Type

# What is Date Closed

Date Closed refers to the specific date when a property transaction is finalized and officially closed. This field is essential for tracking the completion of property deals and ensuring that all related processes are concluded.

The Date Closed field is a custom field within the Property Management system, specifically designed to store the closing date of a property. This field is not mandatory, meaning it can be left empty if the closing date is not yet determined.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Date_Closed__c.field-meta.xml" line="1">

---

The Date Closed field is of type 'Date', ensuring that only date values are stored. This helps maintain data integrity and consistency across the system.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Date_Closed__c</fullName>
    <externalId>false</externalId>
    <label>Date Closed</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Date</type>
</CustomField>
```

---

</SwmSnippet>

## Retrieving Date Closed

# How to Use Date Closed

To utilize the Date Closed field, you can retrieve and manipulate it using various functions provided in the system. These functions help in fetching and accessing the Date Closed value from property records.

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is used to retrieve a record from the Salesforce database. It takes the record ID and the fields to be retrieved as parameters. This function is used to fetch the details of a property, including the Date Closed field.

```javascript
    @wire(getRecord, {
        recordId: '$propertyId',
        fields: [NAME_FIELD, PICTURE_FIELD]
    })
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="45">

---

## Accessing Date Closed Value

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="45:3:3" line-data="        return getFieldValue(this.property.data, NAME_FIELD);">`getFieldValue`</SwmToken> function is used to extract the value of a specific field from a record. This function is useful for accessing the Date Closed field value from the property record fetched using <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken>.

```javascript
        return getFieldValue(this.property.data, NAME_FIELD);
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
