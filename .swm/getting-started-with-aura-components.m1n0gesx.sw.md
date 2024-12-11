---
title: Getting Started with Aura Components
---
## Why Use Aura Components

# Getting Started with Aura Components in User Interface

Aura Components are used to build reusable and modular user interface elements. They allow developers to create components that can be easily integrated and reused across different parts of the application.

## What are Aura Components

Aura Components facilitate the creation of reusable and modular UI elements. This modularity allows for easier maintenance and scalability of the application.

## How to Use Aura Components

Aura Components are the building blocks for creating dynamic web applications. They enable developers to encapsulate HTML, JavaScript, and CSS into reusable units.

## Example of Aura Components

Developers can create Aura Components that are easily integrated and reused across different parts of the application. This is achieved by defining components with specific attributes and methods.

<SwmSnippet path="/force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" line="6">

---

In the file <SwmPath>[force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp](force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp)</SwmPath>, Aura Components are defined with attributes such as <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="6:9:9" line-data="    &lt;aura:attribute name=&quot;left&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`left`</SwmToken>, <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="7:9:9" line-data="    &lt;aura:attribute name=&quot;center&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`center`</SwmToken>, and <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="8:9:9" line-data="    &lt;aura:attribute name=&quot;right&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`right`</SwmToken> to structure the layout.

```cmp
    <aura:attribute name="left" type="Aura.Component[]" access="global" />
    <aura:attribute name="center" type="Aura.Component[]" access="global" />
    <aura:attribute name="right" type="Aura.Component[]" access="global" />
```

---

</SwmSnippet>

## Endpoints of Aura Components

These components communicate using the Lightning Message Service, which facilitates the creation of loosely coupled components. This communication method ensures that components can interact with each other without being tightly bound, enhancing reusability and maintainability.

<SwmSnippet path="/force-app/main/default/lwc/paginator/paginator.js" line="15">

---

Endpoints in Aura Components are functions that handle specific actions or events. For example, the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="15:1:1" line-data="    handlePrevious() {">`handlePrevious`</SwmToken> function in the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="5:6:6" line-data="export default class Paginator extends LightningElement {">`Paginator`</SwmToken> component dispatches a custom event named 'previous' to notify other components that the user wants to navigate to the previous page.

```javascript
    handlePrevious() {
        this.dispatchEvent(new CustomEvent('previous'));
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/paginator/paginator.js" line="18">

---

Similarly, the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="19:1:1" line-data="    handleNext() {">`handleNext`</SwmToken> function in the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="5:6:6" line-data="export default class Paginator extends LightningElement {">`Paginator`</SwmToken> component dispatches a custom event named 'next' to notify other components that the user wants to navigate to the next page.

```javascript

    handleNext() {
        this.dispatchEvent(new CustomEvent('next'));
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
