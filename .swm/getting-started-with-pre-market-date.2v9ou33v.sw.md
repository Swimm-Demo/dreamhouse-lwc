---
title: Getting Started with Pre Market Date
---
# Getting Started with Pre Market Date

The Pre Market Date refers to a custom field in the Property Management module.

This field is used to store the date when a property is set to be available on the market.

It is not a required field, meaning it can be left empty if the information is not available.

## Usage Example

Additionally, the field does not track feed history, history, or trending data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Date_Pre_Market__c.field-meta.xml" line="1">

---

An example of the Date Pre Market field can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Date_Pre_Market__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Date_Pre_Market__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Date_Pre_Market__c</fullName>
    <externalId>false</externalId>
    <label>Date Pre Market</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Date</type>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" line="29">

---

## Endpoints of Date Pre Market

The <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function is used to retrieve the record data for a specific property based on its ID. This function is wired to the <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:14:14" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`propertyId`</SwmToken> and fetches the fields defined in the <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:21:21" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`FIELDS`</SwmToken> constant, which includes <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="33:12:12" line-data="            this.dateListed = getFieldValue(data, DATE_LISTED_FIELD);">`DATE_LISTED_FIELD`</SwmToken> and <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="34:12:12" line-data="            this.daysOnMarket = getFieldValue(data, DAYS_ON_MARKET_FIELD);">`DAYS_ON_MARKET_FIELD`</SwmToken>.

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
