---
title: Basic Concepts of Property Picture
---
# Characteristics of Property Picture

# What is Property Picture

The Picture refers to the image associated with a property in the Property Management system. It is stored as a URL in the <SwmToken path="force-app/main/default/flows/Create_property.flow-meta.xml" pos="317:4:4" line-data="            &lt;field&gt;Picture__c&lt;/field&gt;">`Picture__c`</SwmToken> field of the <SwmToken path="force-app/main/default/flows/Create_property.flow-meta.xml" pos="234:4:4" line-data="        &lt;object&gt;Property__c&lt;/object&gt;">`Property__c`</SwmToken> object.

# Displaying Property Picture

The Picture field is not mandatory and does not track history or trends. This means that it is optional to include a picture for a property, and changes to the picture are not recorded over time.

# Usage of Property Picture

The image can be displayed using the `IMAGE` function in formula fields, such as `Picture_IMG__c`. This allows the picture to be shown in various parts of the Property Management system.

# Example Usage

Additionally, the Picture can be set as the main picture or thumbnail for a property. This helps in visually identifying properties quickly.

<SwmSnippet path="/force-app/main/default/flows/Create_property.flow-meta.xml" line="99">

---

The Picture is used in various places such as the <SwmPath>[force-app/main/default/flows/Create_property.flow-meta.xml](force-app/main/default/flows/Create_property.flow-meta.xml)</SwmPath>, <SwmPath>[force-app/main/default/prompts/PropertyFinder.prompt-meta.xml](force-app/main/default/prompts/PropertyFinder.prompt-meta.xml)</SwmPath>, <SwmPath>[force-app/main/default/prompts/PropertyExplorer.prompt-meta.xml](force-app/main/default/prompts/PropertyExplorer.prompt-meta.xml)</SwmPath>, <SwmPath>[force-app/main/default/layouts/Broker__c-Broker Layout.layout-meta.xml](force-app/main/default/layouts/Broker__c-Broker%20Layout.layout-meta.xml)</SwmPath>, <SwmPath>[force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml](force-app/main/default/objects/Broker__c/fields/Picture_IMG__c.field-meta.xml)</SwmPath>, and <SwmPath>[force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml)</SwmPath>.

```xml
            <label>Picture Found</label>
        </rules>
    </decisions>
    <description
    >This flow helps agents creating new properties in just a few clicks. It calculates the geocoded address calling out to a 3rd party service.</description>
    <formulas>
        <description
        >Main picture URL that we&apos;ll use as thumbnail</description>
        <name>main_picture_url</name>
        <dataType>String</dataType>
        <expression
        >&quot;/sfc/servlet.shepherd/version/download/&quot; + {!get_main_content_version.Id}</expression>
    </formulas>
    <interviewLabel>Create Property {!$Flow.CurrentDateTime}</interviewLabel>
    <label>Create Property</label>
    <processMetadataValues>
        <name>BuilderType</name>
        <value>
            <stringValue>LightningFlowBuilder</stringValue>
        </value>
    </processMetadataValues>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="22">

---

# Picture APIs

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to retrieve pictures associated with a property. It takes the property ID as a parameter and returns an array of picture objects, each containing a title and a URL for downloading the picture.

```javascript
    @wire(getPictures, { propertyId: '$recordId' })
    wiredPictures(pictures) {
        this.pictures = pictures;
        if (pictures.data) {
            const files = pictures.data;
            if (Array.isArray(files) && files.length) {
                this.carouselItems = files.map((file) => {
                    return {
                        title: file.Title,
                        url: `/sfc/servlet.shepherd/version/download/${file.Id}`
                    };
                });
            } else {
                this.carouselItems = null;
            }
        }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
