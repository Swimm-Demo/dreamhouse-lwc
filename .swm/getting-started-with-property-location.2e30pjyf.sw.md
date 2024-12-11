---
title: Getting Started with Property Location
---
# What is Property Location

Property Location refers to the geographical coordinates associated with a property. It is a custom field defined within the Property object.

This field is used to store the latitude and longitude of a property, allowing for precise mapping and location-based services.

The Location field is not required, meaning it can be left empty if the geographical coordinates are not available.

# Purpose of Location

The field is displayed in decimal format, which is a common representation for geographical coordinates.

# How to Use Location

The primary purpose of the Location field is to store the latitude and longitude of a property. This enables precise mapping and location-based services, which are essential for various functionalities within the application.

The Location field is defined within the Property object and is displayed in decimal format. This format is commonly used for representing geographical coordinates.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Location__c.field-meta.xml" line="1">

---

The Location field is defined in the file <SwmPath>[force-app/main/default/objects/Property__c/fields/Location__c.field-meta.xml](force-app/main/default/objects/Property__c/fields/Location__c.field-meta.xml)</SwmPath>.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Location__c</fullName>
    <displayLocationInDecimal>true</displayLocationInDecimal>
    <externalId>false</externalId>
    <label>Location</label>
    <required>false</required>
    <scale>7</scale>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Location</type>
</CustomField>
```

---

</SwmSnippet>

## Defining the Location Field

# Main Functions

There are several main functions related to the Location field. These include defining the field, storing geographical coordinates, and displaying the coordinates in decimal format.

<SwmSnippet path="/force-app/main/default/objects/Property__c/fields/Location__c.field-meta.xml" line="1">

---

The Location field is defined within the Property object as a custom field. This field is used to store the geographical coordinates (latitude and longitude) of a property.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CustomField xmlns="http://soap.sforce.com/2006/04/metadata">
    <fullName>Location__c</fullName>
    <displayLocationInDecimal>true</displayLocationInDecimal>
    <externalId>false</externalId>
    <label>Location</label>
    <required>false</required>
    <scale>7</scale>
    <trackFeedHistory>false</trackFeedHistory>
    <trackHistory>false</trackHistory>
    <trackTrending>false</trackTrending>
    <type>Location</type>
</CustomField>
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="18:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields })">`getRecord`</SwmToken>

# Location APIs

There are specific APIs related to the Location field that facilitate its usage within the application.

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="18">

---

The <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="18:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields })">`getRecord`</SwmToken> function is used to retrieve the record data for a specific property based on its ID. It fetches the latitude and longitude fields among others, which are essential for location-based services.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields })
    wiredProperty({ data, error }) {
        if (data) {
            this.property = data;
            this.calculateDistance();
        } else if (error) {
            this.error = error;
            this.property = undefined;
        }
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="29">

---

## <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="30:7:7" line-data="        this.deviceLocationService = getLocationService();">`getLocationService`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="30:7:7" line-data="        this.deviceLocationService = getLocationService();">`getLocationService`</SwmToken> function is used to access the device's location services. It determines whether the application is running on a mobile device or a browser and retrieves the current geographical coordinates accordingly.

```javascript
    async connectedCallback() {
        this.deviceLocationService = getLocationService();
        if (this.deviceLocationService.isAvailable()) {
            // Running on the Salesforce mobile app on a device
            await this.calculateLocationFromMobileDevice();
        } else if (navigator.geolocation) {
            // Running on a browser
            this.calculateLocationFromBrowser();
        } else {
            this.error = { message: 'No location services available' };
        }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
