---
title: Property Management Overview
---
# Property Management Overview

Property Management refers to the various functionalities and components used to manage properties within the application.

## Creating Properties

It includes creating, updating, and viewing property records, as well as filtering and exploring properties based on specific criteria.

## Searching and Exploring Properties

The 'Create Property' flow allows users to add new properties to the system, including setting the main picture and thumbnail for the property.

## Viewing Property Details

The 'Property Finder' and 'Property Explorer' pages enable users to search for properties using different filters and view their details on a map.

## Displaying Property Information

The 'Property' record page displays important details about a property, such as the number of days it has been on the market.

## Importing Property Data

Various components like 'Property Tile List', 'Property Map', 'Property Carousel', and 'Property Summary' are used to display property information in different formats.

# Property Management Endpoints

The 'Sample Property Importer' component allows for the initialization of property and broker data.

## Retrieving Property Records

Property Management Endpoints provide the necessary backend support for managing property data.

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="29">

---

The <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> function is used to retrieve a record by its ID. It is commonly used to fetch property details such as name, address, city, latitude, and longitude. For example, in the `propertyMap` component, <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="29:4:4" line-data="    @wire(getRecord, { recordId: &#39;$propertyId&#39;, fields })">`getRecord`</SwmToken> is wired to fetch property details and update the map markers accordingly.

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

## Retrieving Property Pictures

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="22:4:4" line-data="    @wire(getPictures, { propertyId: &#39;$recordId&#39; })">`getPictures`</SwmToken> function is used to retrieve pictures associated with a property. This function is wired in the `propertyCarousel` component to fetch and display property images in a carousel format. The images are processed and displayed as carousel items, providing a visual representation of the property.

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
