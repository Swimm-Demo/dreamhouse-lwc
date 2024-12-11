---
title: Getting Started with Page Configurations in UI Components
---
# Representation in UI Components

# Introduction to Page Configurations

Page configurations refer to the setup and customization of various pages within the application. These configurations define the layout and components that appear on each page, ensuring that the user interface is tailored to specific needs.

In the UI components, page configurations are represented by XML files that specify the structure and content of different pages. For example, the <SwmPath>[force-app/main/default/flexipages/Broker_Record_Page.flexipage-meta.xml](force-app/main/default/flexipages/Broker_Record_Page.flexipage-meta.xml)</SwmPath> and <SwmPath>[force-app/main/default/flexipages/Property_Record_Page.flexipage-meta.xml](force-app/main/default/flexipages/Property_Record_Page.flexipage-meta.xml)</SwmPath> files define the layouts for the Broker and Property record pages, respectively.

<SwmSnippet path="/force-app/main/default/flexipages/Broker_Record_Page.flexipage-meta.xml" line="371">

---

These XML files include details such as the master label, which provides a human-readable name for the page, and the arrangement of various UI elements. This allows for a consistent and organized presentation of data across different pages.

```xml
    <masterLabel>Broker Record Page</masterLabel>
```

---

</SwmSnippet>

## How Page Configurations are Used

# Layout Configuration Files

Additionally, the layouts directory contains layout configuration files like <SwmPath>[force-app/main/default/layouts/Broker__c-Broker Layout.layout-meta.xml](force-app/main/default/layouts/Broker__c-Broker%20Layout.layout-meta.xml)</SwmPath> and <SwmPath>[force-app/main/default/layouts/Property__c-Property Layout.layout-meta.xml](force-app/main/default/layouts/Property__c-Property%20Layout.layout-meta.xml)</SwmPath>, which further define the structure of the pages associated with specific objects.

## Example of Page Configurations

Page configurations are essential for defining the layout and components that appear on each page, ensuring that the user interface is tailored to specific needs.

In the UI components, page configurations are represented by XML files that specify the structure and content of different pages. For example, the <SwmPath>[force-app/main/default/flexipages/Broker_Record_Page.flexipage-meta.xml](force-app/main/default/flexipages/Broker_Record_Page.flexipage-meta.xml)</SwmPath> and <SwmPath>[force-app/main/default/flexipages/Property_Record_Page.flexipage-meta.xml](force-app/main/default/flexipages/Property_Record_Page.flexipage-meta.xml)</SwmPath> files define the layouts for the Broker and Property record pages, respectively.

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
