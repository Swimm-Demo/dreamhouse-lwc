---
title: Overview of the State Field in Property Management
---
# State Field in Property Management

State refers to a custom field in the Property Management system.

It is used to store the state information of a property.

The field is labeled as 'State' and has a maximum length of 20 characters.

This field is not required, meaning it can be left empty.

It is a text field and does not track feed history, history, or trending.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/State__c.field-meta.xml" line="1">

---

The field configuration can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/State__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/State__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>State__c</fullName>
    <externalId>false</externalId>
    <label>State</label>
    <length>20</length>
    <required>false</required>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
