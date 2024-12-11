---
title: Introduction to Date Listed in Property Management
---
## Custom Field Representation

# Introduction to Date Listed in Property Management

Date Listed refers to the date when a property is listed in the system. This is a crucial piece of information in property management as it helps track how long a property has been on the market.

## Default Value

In the system, Date Listed is represented by the custom field <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Date_Listed__c&lt;/fullName&gt;">`Date_Listed__c`</SwmToken> in the Property object. This field is used to store the date when a property is listed.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" line="1">

---

The default value for the <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Date_Listed__c&lt;/fullName&gt;">`Date_Listed__c`</SwmToken> field is set to 10 days prior to the current date using the formula <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" pos="4:4:10" line-data="    &lt;defaultValue&gt;TODAY() - 10&lt;/defaultValue&gt;">`TODAY() - 10`</SwmToken>. This ensures that the field has a meaningful default value if not explicitly set.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Date_Listed__c</fullName>
    <defaultValue>TODAY() - 10</defaultValue>
    <externalId>false</externalId>
    <label>Date Listed</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Date</type>
</CustomField>
```

---

</SwmSnippet>

# How Date Listed is Used

## Optional Field

The <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Date_Listed__c&lt;/fullName&gt;">`Date_Listed__c`</SwmToken> field is not required, meaning it can be left empty when creating or updating a property record. This provides flexibility in managing property records.

<SwmSnippet path="/force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" line="29">

---

The <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Listed__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Date_Listed__c&lt;/fullName&gt;">`Date_Listed__c`</SwmToken> field is used in various parts of the system to track and manage properties. For example, it is included in the details retrieved by the <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function.

```javascript
    @wire(getRecord, { recordId: '$propertyId', fields: FIELDS })
    wiredRecord({ error, data }) {
        if (data) {
            this.error = undefined;
            this.dateListed = getFieldValue(data, DATE_LISTED_FIELD);
            this.daysOnMarket = getFieldValue(data, DAYS_ON_MARKET_FIELD);
            if (this.daysOnMarket < MAX_DAYS_NORMAL_STATUS) {
                this.status = 'normal';
            } else if (this.daysOnMarket < MAX_DAYS_WARNING_STATUS) {
                this.status = 'warning';
            } else {
                this.status = 'alert';
            }
        } else if (error) {
            this.daysOnMarket = undefined;
            this.dateListed = undefined;
            this.status = undefined;
            this.error = error;
        }
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
