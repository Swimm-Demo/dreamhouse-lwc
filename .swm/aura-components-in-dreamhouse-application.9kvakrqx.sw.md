---
title: Aura Components in Dreamhouse Application
---
# Usage in Dreamhouse Application

# What is Aura Components

Aura Components are used to build reusable components in the Salesforce platform. They are defined using the Aura framework, which allows for the creation of dynamic web applications.

In the Dreamhouse Lightning Web Components Sample Application, Aura Components are utilized to structure the user interface into different sections.

<SwmSnippet path="/force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" line="6">

---

For example, the `pageTemplate_2_7_3` component defines attributes for <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="6:9:9" line-data="    &lt;aura:attribute name=&quot;left&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`left`</SwmToken>, <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="7:9:9" line-data="    &lt;aura:attribute name=&quot;center&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`center`</SwmToken>, and <SwmToken path="force-app/main/default/aura/pageTemplate_2_7_3/pageTemplate_2_7_3.cmp" pos="8:9:9" line-data="    &lt;aura:attribute name=&quot;right&quot; type=&quot;Aura.Component[]&quot; access=&quot;global&quot; /&gt;">`right`</SwmToken> sections, allowing for a flexible layout.

```cmp
    <aura:attribute name="left" type="Aura.Component[]" access="global" />
    <aura:attribute name="center" type="Aura.Component[]" access="global" />
    <aura:attribute name="right" type="Aura.Component[]" access="global" />
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
