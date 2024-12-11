---
title: UI Components Overview
---
# Structure of UI Components

# Overview

UI Components are the building blocks of the user interface in the application. They are implemented using Lightning Web Components (LWC) and are located in the <SwmPath>[force-app/main/default/lwc/](force-app/main/default/lwc/)</SwmPath> directory.

# Reusability and Composition

Each UI component typically consists of HTML, JavaScript, and CSS files that define the structure, behavior, and styling of the component, respectively.

# Interaction with Salesforce

These components are designed to be reusable and can be composed together to create complex user interfaces. For example, the `propertyTileList` component displays a list of property tiles, while the `paginator` component handles pagination.

# Example Usage

UI Components interact with each other and with the Salesforce platform to provide a seamless user experience. They can fetch data from Salesforce, handle user input, and update the UI dynamically based on user actions.

<SwmSnippet path="/force-app/main/default/lwc/propertyTileList/propertyTileList.js" line="1">

---

An example of a UI Component is the `propertyTileList` component, which displays a list of property tiles.

```javascript
import { LightningElement, wire } from 'lwc';
import {
    publish,
    subscribe,
    unsubscribe,
    MessageContext
} from 'lightning/messageService';
import FILTERSCHANGEMC from '@salesforce/messageChannel/FiltersChange__c';
import PROPERTYSELECTEDMC from '@salesforce/messageChannel/PropertySelected__c';
import getPagedPropertyList from '@salesforce/apex/PropertyController.getPagedPropertyList';
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="61:3:3" line-data="    async handleFilesSelected(event) {">`handleFilesSelected`</SwmToken>

# Endpoints of UI Components

Endpoints of UI Components handle specific functionalities within the components.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="61">

---

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="61:3:3" line-data="    async handleFilesSelected(event) {">`handleFilesSelected`</SwmToken> method in the `propertyCarousel` component is responsible for handling the selection of files by the user. It processes each selected file by compressing and resizing the image, converting it to a <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="80:7:7" line-data="                // Convert to base64">`base64`</SwmToken> format, and then creating a file attached to a record in Salesforce.

```javascript
    async handleFilesSelected(event) {
        try {
            const options = {
                resizeMode: 'fill',
                resizeStrategy: 'reduce',
                targetWidth: 500,
                targetHeight: 500,
                compressionQuality: 0.75,
                imageSmoothingEnabled: true,
                preserveTransparency: false,
                backgroundColor: 'white'
            };

            // Process each file individually to allow partial uploads succeed
            /* eslint-disable no-await-in-loop */
            for (const file of event.target.files) {
                // Compress and resize image
                const blob = await processImage(file, options);

                // Convert to base64
                const base64data = await this.blobToBase64(blob);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken> method in the `brokerCard` component is used to navigate to a specific record page in Salesforce. It utilizes the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="32:3:3" line-data="        this[NavigationMixin.Navigate]({">`NavigationMixin`</SwmToken> to perform the navigation based on the broker's ID.

```javascript
    handleNavigateToRecord() {
        this[NavigationMixin.Navigate]({
            type: 'standard__recordPage',
            attributes: {
                recordId: this.brokerId,
                objectApiName: 'Property__c',
                actionName: 'view'
            }
        });
    }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
