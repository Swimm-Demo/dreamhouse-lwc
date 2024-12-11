---
title: Getting Started with Main Thumbnail Image
---
# Getting Started with Main Thumbnail Image

The Main Thumbnail Image is a custom field in the Property Management module that stores the URL of the main thumbnail image for a property.

This field uses a formula to check if the <SwmToken path="force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml" pos="6:6:6" line-data="    &gt;if(ISBLANK(Thumbnail__c), &quot;&quot;, IMAGE(Thumbnail__c, &quot;Picture&quot;, 200, 200))&lt;/formula&gt;">`Thumbnail__c`</SwmToken> field is blank. If it is not blank, it generates an image tag with the URL from <SwmToken path="force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml" pos="6:6:6" line-data="    &gt;if(ISBLANK(Thumbnail__c), &quot;&quot;, IMAGE(Thumbnail__c, &quot;Picture&quot;, 200, 200))&lt;/formula&gt;">`Thumbnail__c`</SwmToken> and sets the dimensions to 200x200 pixels.

## Field Details

The label for this field is 'Main Thumbnail', and it is not a required field, meaning it can be left empty.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml" line="1">

---

The Main Thumbnail Image field is defined in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Thumbnail_IMG__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Thumbnail_IMG__c</fullName>
    <externalId>false</externalId>
    <formula
    >if(ISBLANK(Thumbnail__c), "", IMAGE(Thumbnail__c, "Picture", 200, 200))</formula>
    <formulaTreatBlanksAs>BlankAsZero</formulaTreatBlanksAs>
    <label>Main Thumbnail</label>
    <required>false</required>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

## Example Usage

An example of how the Main Thumbnail Image field is used can be seen in the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="14:6:6" line-data="export default class PropertyCarousel extends LightningElement {">`PropertyCarousel`</SwmToken> component. The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to retrieve pictures associated with a property.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="22">

---

This function is wired to the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="14:6:6" line-data="export default class PropertyCarousel extends LightningElement {">`PropertyCarousel`</SwmToken> component to fetch the images based on the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:14:14" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`recordId`</SwmToken> of the property.

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
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="28">

---

The retrieved images are then processed to create carousel items, each containing a title and a URL for the image. The URL is constructed using the file ID, which is appended to the endpoint `/sfc/servlet.shepherd/version/download/`.

```javascript
                this.carouselItems = files.map((file) => {
                    return {
                        title: file.Title,
                        url: `/sfc/servlet.shepherd/version/download/${file.Id}`
                    };
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
