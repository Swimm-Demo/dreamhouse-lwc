---
title: Introduction to Business Logic Services
---
## Purpose and Functionality

# Introduction to Business Logic Services

Business Logic Services are designed to encapsulate specific functionalities that can be reused across different parts of the application. They help in organizing and managing business logic in a modular and maintainable manner.

## Example: <SwmToken path="force-app/main/default/classes/GeocodingService.cls" pos="1:8:8" line-data="public with sharing class GeocodingService {">`GeocodingService`</SwmToken>

These services provide a structured way to handle complex business operations, ensuring that the logic is centralized and can be easily maintained or updated. By using services, developers can avoid code duplication and promote reusability.

<SwmSnippet path="/force-app/main/default/classes/GeocodingService.cls" line="1">

---

The <SwmToken path="force-app/main/default/classes/GeocodingService.cls" pos="1:8:8" line-data="public with sharing class GeocodingService {">`GeocodingService`</SwmToken> class is an example of a business logic service. It handles the geocoding of addresses by taking a list of addresses, constructing a URL for each address, making an HTTP request to a geocoding API, and returning the computed coordinates.

```apex
public with sharing class GeocodingService {
    private static final String BASE_URL = 'https://nominatim.openstreetmap.org/search?format=json';

    @InvocableMethod(callout=true label='Geocode address')
    public static List<Coordinates> geocodeAddresses(
        List<GeocodingAddress> addresses
    ) {
        List<Coordinates> computedCoordinates = new List<Coordinates>();

        for (GeocodingAddress address : addresses) {
            String geocodingUrl = BASE_URL;
            geocodingUrl += (String.isNotBlank(address.street))
                ? '&street=' + address.street
                : '';
            geocodingUrl += (String.isNotBlank(address.city))
                ? '&city=' + address.city
                : '';
            geocodingUrl += (String.isNotBlank(address.state))
                ? '&state=' + address.state
                : '';
            geocodingUrl += (String.isNotBlank(address.country))
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/classes/GeocodingService.cls" pos="1:8:8" line-data="public with sharing class GeocodingService {">`GeocodingService`</SwmToken> Endpoints

## Service Endpoints

Service endpoints are the interfaces through which the services interact with other parts of the application or external systems. They define the methods and operations that can be performed by the service.

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="1">

---

The <SwmToken path="force-app/main/default/classes/GeocodingService.cls" pos="1:8:8" line-data="public with sharing class GeocodingService {">`GeocodingService`</SwmToken> class provides endpoints for geocoding operations. It constructs URLs for each address, makes HTTP requests to a geocoding API, and processes the responses to return the coordinates.

```javascript
import { LightningElement, wire, api } from 'lwc';
import { getLocationService } from 'lightning/mobileCapabilities';
import { getRecord, getFieldValue } from 'lightning/uiRecordApi';

// Using hardcoded fields due to LWC bug
const LATITUDE_FIELD = 'Property__c.Location__Latitude__s';
const LONGITUDE_FIELD = 'Property__c.Location__Longitude__s';

const fields = [LATITUDE_FIELD, LONGITUDE_FIELD];

export default class PropertyLocation extends LightningElement {
    error;
    deviceLocationService;
    distance;
    location;
    @api recordId;

    @wire(getRecord, { recordId: '$recordId', fields })
    wiredProperty({ data, error }) {
        if (data) {
            this.property = data;
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
