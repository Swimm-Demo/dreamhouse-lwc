---
title: Broker Fields in Broker Management
---
# Broker Fields

Broker Fields are custom fields defined for the Broker object in the Broker Management system. These fields store various attributes related to brokers.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken> field is a unique identifier for each broker, marked as an external ID and of type Number.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Broker_Id__c</fullName>
    <externalId>true</externalId>
    <label>Broker Id</label>
    <precision>18</precision>
    <required>false</required>
    <scale>0</scale>
    <trackTrending>false</trackTrending>
    <type>Number</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Phone__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Phone__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Phone__c&lt;/fullName&gt;">`Phone__c`</SwmToken> and <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="8:14:14" line-data="import MOBILE_PHONE_FIELD from &#39;@salesforce/schema/Broker__c.Mobile_Phone__c&#39;;">`Mobile_Phone__c`</SwmToken> fields store the broker's phone and mobile phone numbers, respectively, both of type Phone.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Phone__c</fullName>
    <externalId>false</externalId>
    <label>Phone</label>
    <required>false</required>
    <trackTrending>false</trackTrending>
    <type>Phone</type>
</CustomField>

```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Title__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Title__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Title__c&lt;/fullName&gt;">`Title__c`</SwmToken> field captures the broker's title, such as 'Manager' or 'Agent', and is of type Text with a maximum length of 30 characters.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Title__c</fullName>
    <externalId>false</externalId>
    <label>Title</label>
    <length>30</length>
    <required>false</required>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture__c&lt;/fullName&gt;">`Picture__c`</SwmToken> field holds the URL to the broker's picture, while the `Picture_IMG__c` field uses a formula to display the image.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Picture__c</fullName>
    <externalId>false</externalId>
    <label>Picture</label>
    <required>false</required>
    <trackTrending>false</trackTrending>
    <type>Url</type>
</CustomField>

```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken>

# Main Functions

There are several main functions in Broker Fields. Some of them are <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/fields/Phone__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Phone__c&lt;/fullName&gt;">`Phone__c`</SwmToken>, <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="8:14:14" line-data="import MOBILE_PHONE_FIELD from &#39;@salesforce/schema/Broker__c.Mobile_Phone__c&#39;;">`Mobile_Phone__c`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/fields/Title__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Title__c&lt;/fullName&gt;">`Title__c`</SwmToken>, <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture__c&lt;/fullName&gt;">`Picture__c`</SwmToken>, `Picture_IMG__c`, and <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="9:14:14" line-data="import EMAIL_FIELD from &#39;@salesforce/schema/Broker__c.Email__c&#39;;">`Email__c`</SwmToken>.

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken> field is a unique identifier for each broker, marked as an external ID and of type Number.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Broker_Id__c</fullName>
    <externalId>true</externalId>
    <label>Broker Id</label>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken>

# Broker Fields Endpoints

Broker Fields Endpoints

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function is used to retrieve records from Salesforce. It is wired to the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="25:1:1" line-data="    property;">`property`</SwmToken> variable in the `brokerCard` component to fetch the property data, including the broker information.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="25">

---

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="25:4:4" line-data="    @wire(getRecord, {">`getRecord`</SwmToken> function is also used in the `propertySummary` component to fetch property details, including broker information.

```javascript
    @wire(getRecord, {
        recordId: '$propertyId',
        fields: [NAME_FIELD, PICTURE_FIELD]
    })
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
