---
title: Understanding Property Fields
---
# Understanding Property Fields

Fields in the Properties directory represent various attributes of a property, such as its description, city, state, address, location, number of baths, tags, number of beds, picture, and price.

Each field is defined in an XML file and includes metadata such as the field's label, length, type, and whether it is required or unique.

For example, the <SwmToken path="force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Description__c&lt;/fullName&gt;">`Description__c`</SwmToken> field is a long text area with a length of 500 characters, while the `City__c` field is a text field with a length of 50 characters.

Fields also include tracking options, such as whether to track feed history, history, or trending data.

## How Fields are Defined

The `Location__c` field, for instance, is a location type field that displays the location in decimal format.

## Examples of Fields

Fields represent various attributes of an object, such as a property, in a structured manner. They are used to store specific pieces of data related to the object.

## Tracking Options in Fields

Each field is defined in an XML file and includes metadata such as the field's label, length, type, and whether it is required or unique. This metadata helps in structuring the data and enforcing data integrity.

## Specific Field Example

For example, the <SwmToken path="force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Description__c&lt;/fullName&gt;">`Description__c`</SwmToken> field is a long text area with a length of 500 characters, while the `City__c` field is a text field with a length of 50 characters. These fields help in capturing detailed information about a property.

Fields also include tracking options, such as whether to track feed history, history, or trending data. This helps in maintaining a history of changes and tracking trends over time.

The `Location__c` field, for instance, is a location type field that displays the location in decimal format. This is useful for capturing precise geographical data.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" line="1">

---

The <SwmToken path="force-app/main/default/objects/Property__c/fields/Description__c.field-meta.xml" pos="3:4:4" line-data="    &lt;fullName&gt;Description__c&lt;/fullName&gt;">`Description__c`</SwmToken> field is defined as a long text area with a length of 500 characters.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Description__c</fullName>
    <externalId>false</externalId>
    <label>Description</label>
    <length>500</length>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>LongTextArea</type>
    <visibleLines>3</visibleLines>
</CustomField>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
