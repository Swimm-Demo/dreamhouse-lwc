---
title: Record Link in Property Management
---
# How Record Link is Used

# What is Record Link

Record Link is a custom field defined in the Property Management module. It is used to generate a URL that links directly to a specific property record.

# Example of Record Link Usage

The field is created using a formula that combines the base URL of the Salesforce instance with the unique identifier of the property record. This formula ensures that the generated link is always accurate and points to the correct record, regardless of the environment in which it is used.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Record_Link__c.field-meta.xml" line="1">

---

An example of the Record Link field can be found in the <SwmPath>[force-app/main/default/objects/Property__c/fields/Record_Link__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Record_Link__c.field-meta.xml)</SwmPath> file.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Record_Link__c</fullName>
    <externalId>false</externalId>
    <formula
    >LEFT($Api.Partner_Server_URL_260, FIND( '/services', $Api.Partner_Server_URL_260))+ Id</formula>
    <formulaTreatBlanksAs>BlankAsZero</formulaTreatBlanksAs>
    <label>Record Link</label>
    <required>false</required>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Text</type>
    <unique>false</unique>
</CustomField>
```

---

</SwmSnippet>

## Generate URL

# Main Functions

There are several main functions in this field, including generating a URL and linking to a property record. We will dive into these functions.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Record_Link__c.field-meta.xml" line="5">

---

The Record Link custom field generates a URL that links directly to a specific property record. This is achieved using a formula that combines the base URL of the Salesforce instance with the unique identifier of the property record.

```xml
    <formula
    >LEFT($Api.Partner_Server_URL_260, FIND( '/services', $Api.Partner_Server_URL_260))+ Id</formula>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Record_Link__c.field-meta.xml" line="3">

---

## Link to Property Record

The generated URL ensures that the link always points to the correct property record, regardless of the environment in which it is used. This is essential for maintaining accurate and reliable links within the Property Management module.

```xml
    <fullName>Record_Link__c</fullName>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`getRecord`</SwmToken>

# Record Link Endpoints

Record Link Endpoints provide functions to interact with property records and their associated data.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="19">

---

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`getRecord`</SwmToken> function is used to retrieve a record by its ID. It is wired to the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:9:9" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`recordId`</SwmToken> property and fetches the fields specified in the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="19:21:21" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: FIELDS })">`FIELDS`</SwmToken> array.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="22">

---

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to retrieve pictures associated with a property. It is wired to the <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:14:14" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`recordId`</SwmToken> property and processes the pictures to create carousel items.

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

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
