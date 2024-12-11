---
title: Overview of Days On Market
---
## Field Properties

# Overview of Days On Market

Days On Market refers to the number of days a property has been listed for sale. It is calculated using the formula <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:4:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`TODAY() - Date_Listed__c`</SwmToken>, where <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:10:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`Date_Listed__c`</SwmToken> is the date the property was listed.

## Calculation

The Days On Market field is a number field with a precision of 18 and a scale of 0. It is not a required field and does not track history or trending.

## Usage Example

Days On Market is calculated using the formula <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:4:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`TODAY() - Date_Listed__c`</SwmToken>, where <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:10:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`Date_Listed__c`</SwmToken> is the date the property was listed. This formula dynamically calculates the number of days from the listing date to the current date.

The Days On Market field is used to track how long a property has been on the market. This information can be valuable for real estate agents and potential buyers to understand the property's market performance.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" line="1">

---

The field <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="7:4:8" line-data="    &lt;label&gt;Days On Market&lt;/label&gt;">`Days On Market`</SwmToken> is defined in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Days_On_Market__c</fullName>
    <externalId>false</externalId>
    <formula>TODAY() - Date_Listed__c</formula>
    <formulaTreatBlanksAs>BlankAsZero</formulaTreatBlanksAs>
    <label>Days On Market</label>
    <precision>18</precision>
    <required>false</required>
    <scale>0</scale>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Number</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

### Days On Market Calculation

## Main Functions

There are several main functions related to Days On Market, including calculation and display. We will dive a little into the calculation.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" line="1">

---

The Days On Market field calculates the number of days a property has been listed for sale. This is done using the formula <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:4:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`TODAY() - Date_Listed__c`</SwmToken>, where <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:10:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`Date_Listed__c`</SwmToken> is the date the property was listed.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Days_On_Market__c</fullName>
    <externalId>false</externalId>
    <formula>TODAY() - Date_Listed__c</formula>
```

---

</SwmSnippet>

### <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken>

## Endpoints of Days On Market

Endpoints of Days On Market

<SwmSnippet path="/force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function is used to retrieve the record data for a property based on its ID. This function is wired to the <SwmToken path="force-app/main/default/lwc/daysOnMarket/daysOnMarket.js" pos="29:14:14" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields: FIELDS })">`propertyId`</SwmToken> and fetches the fields <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="5:10:10" line-data="    &lt;formula&gt;TODAY() - Date_Listed__c&lt;/formula&gt;">`Date_Listed__c`</SwmToken> and <SwmToken path="force-app/main/default/objects/Property__c/fields/Days_On_Market__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Days_On_Market__c&lt;/fullName&gt;">`Days_On_Market__c`</SwmToken>.

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
