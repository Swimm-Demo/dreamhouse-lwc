---
title: Exploring Property Management in User Interface
---
# <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="18:6:6" line-data="export default class PropertyMap extends LightningElement {">`PropertyMap`</SwmToken> Component

# Overview

Property Management in the User Interface involves handling various aspects of property data and its presentation to the user. This includes managing property details such as name, address, city, and geographical coordinates.

# <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="20:6:6" line-data="export default class PropertyListMap extends LightningElement {">`PropertyListMap`</SwmToken> Component

The `propertyMap` component uses global constants to define fields like <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="10:12:14" line-data="import NAME_FIELD from &#39;@salesforce/schema/Property__c.Name&#39;;">`Property__c.Name`</SwmToken> and <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="12:2:4" line-data="    &#39;Property__c.Address__c&#39;,">`Property__c.Address__c`</SwmToken>, which are essential for displaying property information on a map.

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="16">

---

The `propertyListMap` component manages the state of the map using constants like <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="16:2:2" line-data="const LEAFLET_NOT_LOADED = 0;">`LEAFLET_NOT_LOADED`</SwmToken> and <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="18:2:2" line-data="const LEAFLET_READY = 2;">`LEAFLET_READY`</SwmToken>, ensuring that properties are only displayed when the map is ready.

```javascript
const LEAFLET_NOT_LOADED = 0;
const LEAFLET_LOADING = 1;
const LEAFLET_READY = 2;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertySummary/propertySummary.js" line="44">

---

# <SwmToken path="force-app/main/default/lwc/propertySummary/propertySummary.js" pos="17:6:6" line-data="export default class PropertySummary extends NavigationMixin(LightningElement) {">`PropertySummary`</SwmToken> Component

The `propertySummary` component handles the selection of properties by setting and getting the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:14:14" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`propertyId`</SwmToken>, which is crucial for displaying detailed information about a selected property.

```javascript
    get propertyName() {
        return getFieldValue(this.property.data, NAME_FIELD);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="19">

---

# <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="11:6:6" line-data="export default class PropertyLocation extends LightningElement {">`PropertyLocation`</SwmToken> Component

In the `propertyLocation` component, the <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="21:3:3" line-data="            this.property = data;">`property`</SwmToken> data is wired and used to calculate distances, enhancing the user experience by providing relevant location-based information.

```javascript
    wiredProperty({ data, error }) {
        if (data) {
            this.property = data;
            this.calculateDistance();
        } else if (error) {
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken>

# Property Management Endpoints

Property Management Endpoints are used to retrieve and manage property data within the application.

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> function is used to retrieve property records by their ID. This function is wired to various components to fetch property details such as name, address, city, and geographical coordinates.

```javascript
    @wire(getRecord, { recordId: '$propertyId', fields })
    wiredRecord({ error, data }) {
        if (data) {
            this.error = undefined;
            const property = data.fields;
            this.address = `${property.Address__c.value}, ${property.City__c.value}`;
            this.markers = [
                {
                    location: {
                        Latitude: property.Location__Latitude__s.value,
                        Longitude: property.Location__Longitude__s.value
                    },
                    title: `${property.Name.value}`,
                    description: `<b>Address</b>: ${property.Address__c.value}`,
                    mapIcon: {
                        path: 'M1472 992v480q0 26-19 45t-45 19h-384v-384h-256v384h-384q-26 0-45-19t-19-45v-480q0-1 .5-3t.5-3l575-474 575 474q1 2 1 6zm223-69l-62 74q-8 9-21 11h-3q-13 0-21-7l-692-577-692 577q-12 8-24 7-13-2-21-11l-62-74q-8-10-7-23.5t11-21.5l719-599q32-26 76-26t76 26l244 204v-195q0-14 9-23t23-9h192q14 0 23 9t9 23v408l219 182q10 8 11 21.5t-7 23.5z',
                        fillColor: '#f28b00',
                        fillOpacity: 1,
                        strokeWeight: 1,
                        scale: 0.02
                    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="22">

---

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to fetch pictures associated with a property. This function is wired to the `propertyCarousel` component to display a carousel of property images.

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
