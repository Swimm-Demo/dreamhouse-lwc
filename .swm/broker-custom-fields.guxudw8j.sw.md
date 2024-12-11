---
title: Broker Custom Fields
---
# Key Broker Custom Fields

# Overview of Broker Custom Fields

Broker Custom Fields refer to the custom fields defined for the Broker object. These fields capture various attributes related to a broker, enabling detailed tracking and management of broker information.

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Broker_Id__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Broker_Id__c&lt;/fullName&gt;">`Broker_Id__c`</SwmToken>

Several key custom fields are defined for the Broker object, each serving a specific purpose in capturing broker-related data.

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

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Phone__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Phone__c&lt;/fullName&gt;">`Phone__c`</SwmToken> and Mobile_Phone__c

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Phone__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Phone__c&lt;/fullName&gt;">`Phone__c`</SwmToken> and `Mobile_Phone__c` fields store the broker's phone and mobile phone numbers, respectively, both of type Phone.

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

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Title__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Title__c&lt;/fullName&gt;">`Title__c`</SwmToken>

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Title__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Title__c&lt;/fullName&gt;">`Title__c`</SwmToken> field captures the broker's title, such as 'Manager' or 'Agent', and is of type Text with a length of 30 characters.

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

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture__c&lt;/fullName&gt;">`Picture__c`</SwmToken> and <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture_IMG__c&lt;/fullName&gt;">`Picture_IMG__c`</SwmToken>

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture__c&lt;/fullName&gt;">`Picture__c`</SwmToken> field holds the URL to the broker's picture. The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture_IMG__c&lt;/fullName&gt;">`Picture_IMG__c`</SwmToken> field uses a formula to display the image from the URL stored in <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture__c&lt;/fullName&gt;">`Picture__c`</SwmToken>.

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

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Picture_IMG__c&lt;/fullName&gt;">`Picture_IMG__c`</SwmToken> field uses a formula to display the image from the URL stored in <SwmToken path="force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml" pos="5:7:7" line-data="    &lt;formula&gt;IMAGE( Picture__c , &quot;picture&quot; , 150, 150)&lt;/formula&gt;">`Picture__c`</SwmToken>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Picture_IMG__c</fullName>
    <externalId>false</externalId>
    <formula>IMAGE( Picture__c , "picture" , 150, 150)</formula>
    <formulaTreatBlanksAs>BlankAsZero</formulaTreatBlanksAs>
    <label>Picture</label>
    <required>false</required>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Broker__c/fields/Email__c.field-meta.xml" line="1">

---

## <SwmToken path="force-app/main/default/objects/Broker__c/fields/Email__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Email__c&lt;/fullName&gt;">`Email__c`</SwmToken>

The <SwmToken path="force-app/main/default/objects/Broker__c/fields/Email__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Email__c&lt;/fullName&gt;">`Email__c`</SwmToken> field stores the broker's email address and is of type Email.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Email__c</fullName>
    <externalId>false</externalId>
    <label>Email</label>
    <required>false</required>
    <trackTrending>false</trackTrending>
    <type>Email</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
