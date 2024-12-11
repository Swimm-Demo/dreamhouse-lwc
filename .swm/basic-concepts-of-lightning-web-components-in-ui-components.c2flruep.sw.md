---
title: Basic Concepts of Lightning Web Components in UI Components
---
# Usage in Dreamhouse Application

# Basic Concepts of Lightning Web Components

Lightning Web Components (LWC) are a modern framework for building user interfaces on the Salesforce platform. They leverage web standards and provide a lightweight, performant way to create reusable components.

# Structure of Lightning Web Components

In the Dreamhouse application, LWCs are used to build various UI components that enhance user productivity and engagement. These components include property listings, property details, and other interactive elements.

# Example Components

Each LWC is defined by a JavaScript file, an HTML template, and a metadata configuration file. The JavaScript file contains the component's logic, the HTML template defines the structure, and the metadata file specifies the component's properties and visibility.

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/propertyTile.js-meta.xml" line="1">

---

For example, the `propertyTile` component displays individual property details, while the `propertyTileList` component shows a list of properties. These components interact with each other to provide a seamless user experience.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
    <apiVersion>61.0</apiVersion>
    <isExposed>false</isExposed>
</LightningComponentBundle>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/paginator/paginator.js" line="15">

---

# Event Handling in Lightning Web Components

Endpoints in Lightning Web Components handle various user interactions. For instance, the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="15:1:1" line-data="    handlePrevious() {">`handlePrevious`</SwmToken> function manages the event when the user wants to navigate to the previous page. It dispatches a custom event named 'previous' to notify other components or services about this action.

```javascript
    handlePrevious() {
        this.dispatchEvent(new CustomEvent('previous'));
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/paginator/paginator.js" line="18">

---

Similarly, the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="19:1:1" line-data="    handleNext() {">`handleNext`</SwmToken> function handles the event when the user wants to navigate to the next page. It dispatches a custom event named 'next' to notify other components or services about this action.

```javascript

    handleNext() {
        this.dispatchEvent(new CustomEvent('next'));
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
