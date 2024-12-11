---
title: Overview of Message Channels in Integrations
---
## FiltersChange Message Channel

# Overview of Message Channels

Message Channels are used to facilitate communication between different Lightning Web Components (LWCs) in the application. They enable components to send and receive messages without having direct references to each other, promoting a decoupled architecture.

<SwmSnippet path="/force-app/main/default/messageChannels/FiltersChange.messageChannel-meta.xml" line="1">

---

The `FiltersChange` message channel is used to communicate changes in search filters. It includes fields such as <SwmToken path="force-app/main/default/messageChannels/FiltersChange.messageChannel-meta.xml" pos="6:4:4" line-data="        &lt;fieldName&gt;searchKey&lt;/fieldName&gt;">`searchKey`</SwmToken>, <SwmToken path="force-app/main/default/messageChannels/FiltersChange.messageChannel-meta.xml" pos="10:4:4" line-data="        &lt;fieldName&gt;maxPrice&lt;/fieldName&gt;">`maxPrice`</SwmToken>, <SwmToken path="force-app/main/default/messageChannels/FiltersChange.messageChannel-meta.xml" pos="14:4:4" line-data="        &lt;fieldName&gt;minBedrooms&lt;/fieldName&gt;">`minBedrooms`</SwmToken>, and <SwmToken path="force-app/main/default/messageChannels/FiltersChange.messageChannel-meta.xml" pos="18:4:4" line-data="        &lt;fieldName&gt;minBathrooms&lt;/fieldName&gt;">`minBathrooms`</SwmToken>, which represent the various filter criteria.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<LightningMessageChannel xmlns="http://soap.sforce.com/2006/04/metadata">
    <isExposed>true</isExposed>
    <lightningMessageFields>
        <description>Search Key</description>
        <fieldName>searchKey</fieldName>
    </lightningMessageFields>
    <lightningMessageFields>
        <description>Max Price</description>
        <fieldName>maxPrice</fieldName>
    </lightningMessageFields>
    <lightningMessageFields>
        <description>Minimum number of Bedrooms</description>
        <fieldName>minBedrooms</fieldName>
    </lightningMessageFields>
    <lightningMessageFields>
        <description>Minimum number of Bathrooms</description>
        <fieldName>minBathrooms</fieldName>
    </lightningMessageFields>
    <masterLabel>Filters Change Message Channel</masterLabel>
</LightningMessageChannel>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/messageChannels/PropertySelected.messageChannel-meta.xml" line="1">

---

## PropertySelected Message Channel

The `PropertySelected` message channel is used to communicate the selection of a property. It includes a field called <SwmToken path="force-app/main/default/messageChannels/PropertySelected.messageChannel-meta.xml" pos="6:4:4" line-data="        &lt;fieldName&gt;propertyId&lt;/fieldName&gt;">`propertyId`</SwmToken>, which identifies the selected property.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<LightningMessageChannel xmlns="http://soap.sforce.com/2006/04/metadata">
    <isExposed>true</isExposed>
    <lightningMessageFields>
        <description>Property Id</description>
        <fieldName>propertyId</fieldName>
    </lightningMessageFields>
    <masterLabel>Property Selected Message Channel</masterLabel>
</LightningMessageChannel>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
