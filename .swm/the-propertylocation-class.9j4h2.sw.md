---
title: The PropertyLocation class
---
This document will cover the class <SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken>. We will explain:

1. What <SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken> is.
2. The variables and functions defined in <SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken>.

# Variables and functions

# What is <SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken>

<SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken> is a Lightning Web Component (LWC) defined in the file <SwmPath>[force-app/main/default/lwc/propertyLocation/propertyLocation.js](force-app/main/default/lwc/propertyLocation/propertyLocation.js)</SwmPath>. It is used to calculate the distance between a property and the user's current location. This component leverages the Salesforce mobile capabilities and browser geolocation services to determine the user's location and then calculates the distance to the property using the Haversine formula.

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="18">

---

The function <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="19:1:1" line-data="    wiredProperty({ data, error }) {">`wiredProperty`</SwmToken> is a wired function that retrieves the property record based on the <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="18:9:9" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields })">`recordId`</SwmToken>. It calculates the distance to the property if the data is successfully retrieved.

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

The function <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="29:3:3" line-data="    async connectedCallback() {">`connectedCallback`</SwmToken> is an asynchronous function that initializes the device location service and determines whether the component is running on a mobile device or a browser. It then calls the appropriate function to calculate the location.

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
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="42">

---

The function <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="42:3:3" line-data="    async calculateLocationFromMobileDevice() {">`calculateLocationFromMobileDevice`</SwmToken> is an asynchronous function that retrieves the current position from the mobile device's location service and then calculates the distance to the property.

```javascript
    async calculateLocationFromMobileDevice() {
        try {
            this.location = await this.deviceLocationService.getCurrentPosition(
                {
                    enableHighAccuracy: true
                }
            );
            this.calculateDistance();
        } catch (error) {
            this.error = error;
        }
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="55">

---

The function <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="55:1:1" line-data="    calculateLocationFromBrowser() {">`calculateLocationFromBrowser`</SwmToken> retrieves the current position using the browser's geolocation API and then calculates the distance to the property.

```javascript
    calculateLocationFromBrowser() {
        navigator.geolocation.getCurrentPosition(
            (result) => {
                this.location = result;
                this.calculateDistance();
            },
            (error) => {
                this.error = error;
            }
        );
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/propertyLocation.js" line="67">

---

The function <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="67:1:1" line-data="    calculateDistance() {">`calculateDistance`</SwmToken> calculates the distance between the user's current location and the property using the Haversine formula. It updates the <SwmToken path="force-app/main/default/lwc/propertyLocation/propertyLocation.js" pos="87:3:3" line-data="            this.distance = d / 1.609344;">`distance`</SwmToken> field with the calculated value.

```javascript
    calculateDistance() {
        if (this.location && this.property) {
            const latitude1 = this.location.coords.latitude;
            const latitude2 = getFieldValue(this.property, LATITUDE_FIELD);
            const longitude1 = this.location.coords.longitude;
            const longitude2 = getFieldValue(this.property, LONGITUDE_FIELD);

            // Haversine formula
            const deg2rad = (deg) => (deg * Math.PI) / 180.0;
            const earthRadius = 6371; // Radius of the earth in km
            const dLat = deg2rad(latitude2 - latitude1); // deg2rad below
            const dLon = deg2rad(longitude2 - longitude1);
            const a =
                Math.sin(dLat / 2) * Math.sin(dLat / 2) +
                Math.cos(deg2rad(latitude1)) *
                    Math.cos(deg2rad(latitude2)) *
                    Math.sin(dLon / 2) *
                    Math.sin(dLon / 2);
            const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1 - a));
            const d = earthRadius * c;
            this.distance = d / 1.609344;
```

---

</SwmSnippet>

# Usage

<SwmSnippet path="/force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" line="46">

---

## <SwmPath>[force-app/main/default/lwc/propertyLocation/\__tests_\_/propertyLocation.test.js](force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js)</SwmPath>

The <SwmToken path="force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js" pos="48:4:4" line-data="            is: PropertyLocation">`PropertyLocation`</SwmToken> class is used in the <SwmPath>[force-app/main/default/lwc/propertyLocation/\__tests_\_/propertyLocation.test.js](force-app/main/default/lwc/propertyLocation/__tests__/propertyLocation.test.js)</SwmPath> file to test various scenarios related to property location functionalities. For instance, it is used to render an error panel when no location services are available.

```javascript
    it('renders an error panel when no location services are available', async () => {
        const element = createElement('c-property-location', {
            is: PropertyLocation
        });

        document.body.appendChild(element);
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
