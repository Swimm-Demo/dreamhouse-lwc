---
title: Exploring Main Property Picture
---
# Exploring Main Property Picture

The main property picture is a crucial visual element in the Property Management module, providing a primary image representation of a property.

The custom field <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:22:22" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`Picture`</SwmToken>` IMG` is specifically defined to display this main picture. It is implemented within the Property Management module.

This field utilizes a formula to determine if the <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:8:8" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`Picture__c`</SwmToken> field is blank. If the <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:8:8" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`Picture__c`</SwmToken> field contains an image, the <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:16:16" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`IMAGE`</SwmToken> function is used to display it.

The label for this field is 'Main Picture', clearly indicating its purpose to show the primary image associated with the property.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" line="1">

---

An example of the <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:22:22" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`Picture`</SwmToken>` IMG` field's definition can be found in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Picture_IMG__c</fullName>
    <externalId>false</externalId>
    <formula>if(ISBLANK(Picture__c), '', IMAGE(Picture__c, "Picture"))</formula>
    <formulaTreatBlanksAs>BlankAsZero</formulaTreatBlanksAs>
    <label>Main Picture</label>
    <required>false</required>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

# Picture IMG Endpoints

The <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="48:3:3" line-data="    get pictureURL() {">`pictureURL`</SwmToken> endpoint is used to retrieve the URL of the main picture associated with a property. This URL is derived from the <SwmToken path="force-app/main/default/objects/Property__c/fields/Picture_IMG__c.field-meta.xml" pos="5:8:8" line-data="    &lt;formula&gt;if(ISBLANK(Picture__c), &#39;&#39;, IMAGE(Picture__c, &quot;Picture&quot;))&lt;/formula&gt;">`Picture__c`</SwmToken> field of the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="10:12:12" line-data="import NAME_FIELD from &#39;@salesforce/schema/Property__c.Name&#39;;">`Property__c`</SwmToken> object.

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="48">

---

In the `propertySummary` component, the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="48:3:3" line-data="    get pictureURL() {">`pictureURL`</SwmToken> is accessed to display the main picture of a property.

```javascript
    get pictureURL() {
        return getFieldValue(this.property.data, PICTURE_FIELD);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.html" line="13">

---

Within the <SwmPath>[force-app/main/default/lwc/propertySummary/propertySummary.html](force-app/main/default/lwc/propertySummary/propertySummary.html)</SwmPath> file, the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.html" pos="14:4:4" line-data="                    src={pictureURL}">`pictureURL`</SwmToken> is used as the <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.html" pos="14:1:1" line-data="                    src={pictureURL}">`src`</SwmToken> attribute of an <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.html" pos="13:2:2" line-data="                &lt;img">`img`</SwmToken> tag to display the property picture.

```html
                <img
                    src={pictureURL}
                    alt="Property picture"
                    class="slds-var-m-bottom_x-small"
                />
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
