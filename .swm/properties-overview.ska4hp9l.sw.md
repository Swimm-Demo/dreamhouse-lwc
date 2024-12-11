---
title: Properties Overview
---
# Properties Overview

Properties refer to the custom object `Property__c` which is defined in the metadata file <SwmPath>[force-app/main/default/objects/Property__c/Property__c.object-meta.xml](force-app/main/default/objects/Property__c/Property__c.object-meta.xml)</SwmPath>. This object includes various action overrides such as Accept, <SwmToken path="force-app/main/default/objects/Property__c/Property__c.object-meta.xml" pos="8:4:4" line-data="        &lt;actionName&gt;CancelEdit&lt;/actionName&gt;">`CancelEdit`</SwmToken>, Clone, Delete, Edit, List, New, <SwmToken path="force-app/main/default/objects/Property__c/Property__c.object-meta.xml" pos="32:4:4" line-data="        &lt;actionName&gt;SaveEdit&lt;/actionName&gt;">`SaveEdit`</SwmToken>, Tab, and View, all set to their default types.

The `Property__c` object is configured with several features enabled, including activities, bulk API, feeds, history, reports, search, sharing, and streaming API. It is labeled as 'Property' and has a plural label 'Properties'.

The name field for the `Property__c` object is labeled 'Property Name' and is of type Text. The sharing model for this object is set to <SwmToken path="force-app/main/default/objects/Property__c/Property__c.object-meta.xml" pos="64:4:4" line-data="    &lt;sharingModel&gt;ReadWrite&lt;/sharingModel&gt;">`ReadWrite`</SwmToken>, and its visibility is public.

Additionally, there is a compact layout defined for the `Property__c` object in the file <SwmPath>[force-app/main/default/objects/Property__c/compactLayouts/Property_Compact_Layout.compactLayout-meta.xml](force-app/main/default/objects/Property__c/compactLayouts/Property_Compact_Layout.compactLayout-meta.xml)</SwmPath>. This layout includes fields such as Name, City__c, Price__c, Beds__c, and Baths__c.

The `Property__c` object also has several custom fields defined in the `fields` directory, including Record_Link__c, Description__c, Date_Contracted__c, Baths__c, Date_Pre_Market__c, Thumbnail_IMG__c, Date_Agreement__c, Beds__c, City__c, Status__c, Broker__c, Price_Sold__c, Zip__c, Assessed_Value__c, Thumbnail__c, Picture_IMG__c, Tags__c, State__c, Days_On_Market__c, Date_Listed__c, Price__c, Picture__c, Date_Closed__c, Location__c, and Address__c.

<SwmSnippet path="/force-app/main/default/objects/Property__c/Property__c.object-meta.xml" line="3">

---

The `Property__c` object includes action overrides for actions like Accept, <SwmToken path="force-app/main/default/objects/Property__c/Property__c.object-meta.xml" pos="8:4:4" line-data="        &lt;actionName&gt;CancelEdit&lt;/actionName&gt;">`CancelEdit`</SwmToken>, Clone, Delete, Edit, List, New, <SwmToken path="force-app/main/default/objects/Property__c/Property__c.object-meta.xml" pos="32:4:4" line-data="        &lt;actionName&gt;SaveEdit&lt;/actionName&gt;">`SaveEdit`</SwmToken>, Tab, and View, all set to their default types.

```xml
    <actionOverrides>
        <actionName>Accept</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>CancelEdit</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Clone</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Delete</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
        <actionName>Edit</actionName>
        <type>Default</type>
    </actionOverrides>
    <actionOverrides>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
