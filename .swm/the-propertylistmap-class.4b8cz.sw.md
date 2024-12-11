---
title: The PropertyListMap class
---
This document will cover the class <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken>. We will cover:

1. What <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken> is.
2. Variables and functions defined in <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken>.

# Variables and functions

# What is <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken>

<SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken> is a Lightning Web Component (LWC) defined in the file <SwmPath>[force-app/main/default/lwc/propertyListMap/propertyListMap.js](force-app/main/default/lwc/propertyListMap/propertyListMap.js)</SwmPath>. It is used to display a list of properties on a map using the Leaflet library. The component handles the loading of property data, rendering the map, and displaying property markers with tooltips.

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="47">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="47:1:1" line-data="    wiredProperties({ error, data }) {">`wiredProperties`</SwmToken> is used to wire the property list data from the server. It updates the <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="49:3:3" line-data="            this.properties = data.records;">`properties`</SwmToken> array and calls <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="51:3:3" line-data="            this.displayProperties();">`displayProperties`</SwmToken> to render the properties on the map.

```javascript
    wiredProperties({ error, data }) {
        if (data) {
            this.properties = data.records;
            // Display properties on map
            this.displayProperties();
        } else if (error) {
            this.properties = [];
            this.dispatchEvent(
                new ShowToastEvent({
                    title: 'Error loading properties',
                    message: error.message,
                    variant: 'error'
                })
            );
        }
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="64">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="64:1:1" line-data="    connectedCallback() {">`connectedCallback`</SwmToken> subscribes to the <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="67:1:1" line-data="            FILTERS_CHANGED,">`FILTERS_CHANGED`</SwmToken> message channel to handle filter changes.

```javascript
    connectedCallback() {
        this.subscription = subscribe(
            this.messageContext,
            FILTERS_CHANGED,
            (message) => {
                this.handleFilterChange(message);
            }
        );
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="74">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="74:1:1" line-data="    disconnectedCallback() {">`disconnectedCallback`</SwmToken> unsubscribes from the message channel to clean up resources.

```javascript
    disconnectedCallback() {
        unsubscribe(this.subscription);
        this.subscription = null;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="79">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="79:3:3" line-data="    async renderedCallback() {">`renderedCallback`</SwmToken> initializes the Leaflet map if it is not already loaded.

```javascript
    async renderedCallback() {
        if (this.leafletState === LEAFLET_NOT_LOADED) {
            await this.initializeLeaflet();
        }
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="85">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="85:3:3" line-data="    async initializeLeaflet() {">`initializeLeaflet`</SwmToken> loads the Leaflet library and configures the map.

```javascript
    async initializeLeaflet() {
        try {
            // Leaflet is loading
            this.leafletState = LEAFLET_LOADING;

            // Load resource files
            await Promise.all([
                loadScript(this, `${LEAFLET}/leaflet.js`),
                loadStyle(this, `${LEAFLET}/leaflet.css`)
            ]);

            // Configure map
            const mapElement = this.template.querySelector('.map');
            this.map = L.map(mapElement, {
                zoomControl: true,
                tap: false
                // eslint-disable-next-line no-magic-numbers
            });
            this.map.setView([42.356045, -71.08565], 13);
            this.map.scrollWheelZoom.disable();
            L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="127">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="127:1:1" line-data="    displayProperties() {">`displayProperties`</SwmToken> renders the property markers on the map.

```javascript
    displayProperties() {
        // Stop if leaflet isn't ready yet
        if (this.leafletState !== LEAFLET_READY) {
            return;
        }

        // Remove previous property layer form map if it exits
        if (this.propertyLayer) {
            this.map.removeLayer(this.propertyLayer);
        }

        // Prepare property icon
        const icon = L.divIcon({
            className: 'my-div-icon',
            html: '<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 52 52"><path fill="#DB4437" d="m26 2c-10.5 0-19 8.5-19 19.1 0 13.2 13.6 25.3 17.8 28.5 0.7 0.6 1.7 0.6 2.5 0 4.2-3.3 17.7-15.3 17.7-28.5 0-10.6-8.5-19.1-19-19.1z m0 27c-4.4 0-8-3.6-8-8s3.6-8 8-8 8 3.6 8 8-3.6 8-8 8z"></path></svg>'
        });

        // Prepare click handler for property marker
        const markerClickHandler = (event) => {
            // Send message using the Lightning Message Service
            const message = { propertyId: event.target.propertyId };
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="170">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="170:1:1" line-data="    handleFilterChange(filters) {">`handleFilterChange`</SwmToken> updates the filter values based on the received message.

```javascript
    handleFilterChange(filters) {
        this.searchKey = filters.searchKey;
        this.maxPrice = filters.maxPrice;
        this.minBedrooms = filters.minBedrooms;
        this.minBathrooms = filters.minBathrooms;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/propertyListMap.js" line="177">

---

The function <SwmToken path="force-app/main/default/lwc/propertyListMap/propertyListMap.js" pos="177:1:1" line-data="    getTooltipMarkup(property) {">`getTooltipMarkup`</SwmToken> generates the HTML markup for the property tooltip.

```javascript
    getTooltipMarkup(property) {
        return `<div class="tooltip-picture" style="background-image:url(${property.Thumbnail__c})">  
  <div class="lower-third">
    <h1>${property.Name}</h1>
    <p>Beds: ${property.Beds__c} - Baths: ${property.Baths__c}</p>
  </div>
</div>`;
    }
```

---

</SwmSnippet>

# Usage

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" line="84">

---

## Registering Property Filters Subscriber

The <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="87:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken> class is used to register a property filters subscriber during the component lifecycle. This is demonstrated by creating an instance of the component and appending it to the document body.

```javascript
    it('registers propertyFilters subscriber during the component lifecycle', () => {
        // Create component
        const element = createElement('c-property-list-map', {
            is: PropertyListMap
        });
        document.body.appendChild(element);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" line="96">

---

## Loading Leaflet Resources

The <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="99:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken> class is also used to load the Leaflet JavaScript and CSS static resources. This is achieved by creating an instance of the component and appending it to the document body.

```javascript
    it('loads the leaflet javascript and css static resources', () => {
        // Create component
        const element = createElement('c-property-list-map', {
            is: PropertyListMap
        });
        document.body.appendChild(element);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" line="140">

---

## Firing Toast Event

Additionally, the <SwmToken path="force-app/main/default/lwc/propertyListMap/__tests__/propertyListMap.test.js" pos="143:4:4" line-data="            is: PropertyListMap">`PropertyListMap`</SwmToken> class is used to fire a toast event when properties cannot be retrieved. This is done by creating an instance of the component and appending it to the document body.

```javascript
    it('fires a toast event when properties cannot be retrieved', async () => {
        // Create component
        const element = createElement('c-property-list-map', {
            is: PropertyListMap
        });
        document.body.appendChild(element);
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
