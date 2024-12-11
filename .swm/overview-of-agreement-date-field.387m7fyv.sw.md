---
title: Overview of Agreement Date Field
---
# Basic Concepts of Agreement Date

The Agreement Date refers to a custom field in the Property Management module.

It is used to store the date when an agreement related to a property is made.

This field is not required, meaning it can be left empty if the date is not available.

The Agreement Date field does not track feed history, history, or trending data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Date_Agreement__c.field-meta.xml" line="1">

---

For example, in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Date_Agreement__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Date_Agreement__c.field-meta.xml)</SwmPath>, the Agreement Date field is defined with the type <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Agreement__c.field-meta.xml" pos="5:4:4" line-data="    &lt;label&gt;Date Agreement&lt;/label&gt;">`Date`</SwmToken> and is labeled as <SwmToken path="force-app/main/default/objects/Property__c/fields/Date_Agreement__c.field-meta.xml" pos="5:4:6" line-data="    &lt;label&gt;Date Agreement&lt;/label&gt;">`Date Agreement`</SwmToken>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Date_Agreement__c</fullName>
    <externalId>false</externalId>
    <label>Date Agreement</label>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Date</type>
</CustomField>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken>

# Date Agreement Endpoints

The Date Agreement field can be accessed and manipulated through various endpoints.

<SwmSnippet path="/force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record from Salesforce based on the provided record ID and fields. In the context of the Agreement Date, it is used to fetch the property record that includes the Agreement Date field.

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

<SwmSnippet path="/force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" line="33">

---

## <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="33:7:7" line-data="            this.dateListed = getFieldValue(data, DATE_LISTED_FIELD);">`getFieldValue`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="33:7:7" line-data="            this.dateListed = getFieldValue(data, DATE_LISTED_FIELD);">`getFieldValue`</SwmToken> function is used to extract the value of a specific field from a record. For the Agreement Date, this function is used to retrieve the date when an agreement related to a property is made.

```javascript
            this.dateListed = getFieldValue(data, DATE_LISTED_FIELD);
            this.daysOnMarket = getFieldValue(data, DAYS_ON_MARKET_FIELD);
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
