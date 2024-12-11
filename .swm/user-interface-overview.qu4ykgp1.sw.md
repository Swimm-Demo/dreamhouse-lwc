---
title: User Interface Overview
---
# User Interface Overview

The User Interface (UI) is designed to provide an intuitive and seamless experience for users interacting with the application.

It includes various components such as buttons, panels, and forms that facilitate user interactions and data input.

## Example of UI Usage

These components are built using Lightning Web Components (LWC) and are organized within the <SwmPath>[force-app/main/default/lwc/](force-app/main/default/lwc/)</SwmPath> directory.

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="19">

---

For instance, the <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="19:3:3" line-data="    async handleBeginScanClick() {">`handleBeginScanClick`</SwmToken> method in the `barcodeScanner` component handles the initiation of a QR code scan, providing feedback to the user through toasts and navigation.

```javascript
    async handleBeginScanClick() {
        // Reset scannedQrCode to empty string before starting a new scan
        this.scannedQrCode = '';

        // Make sure BarcodeScanner is available before trying to use it
        // Scan QR Code button also disabled when scanner unavailable
        if (this.myScanner?.isAvailable()) {
            const scanningOptions = {
                barcodeTypes: [this.myScanner.barcodeTypes.QR],
                instructionText: 'Scan a QR Code',
                successText: 'Scanning complete.'
            };

            // Try starting the scanning process, then using the result to navigate to a property record
            try {
                const captureResult =
                    await this.myScanner.beginCapture(scanningOptions);

                // Extract QR code data
                this.scannedQrCode = captureResult.value;

```

---

</SwmSnippet>

## Navigation Functionality

## Error Handling in UI

Additionally, the `ErrorPanel` component is used to display error messages in a user-friendly manner, allowing users to view detailed error information if needed.

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="32:3:5" line-data="        this[NavigationMixin.Navigate]({">`NavigationMixin.Navigate`</SwmToken> function is used to navigate to different records or pages within the Salesforce application. It is commonly used in components to provide navigation functionality based on user interactions.

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
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

For example, in the `brokerCard` component, the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken> method uses <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="32:3:5" line-data="        this[NavigationMixin.Navigate]({">`NavigationMixin.Navigate`</SwmToken> to navigate to the broker's record page when a button is clicked.

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
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

## Data Retrieval

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> function from <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="2:14:16" line-data="import { getRecord, getFieldValue } from &#39;lightning/uiRecordApi&#39;;">`lightning/uiRecordApi`</SwmToken> is used to retrieve records from the Salesforce database. It is often used in conjunction with the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:1:2" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`@wire`</SwmToken> decorator to automatically fetch and update data as needed.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="24">

---

In the `brokerCard` component, <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:4:4" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`getRecord`</SwmToken> is used to fetch the property record based on the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="24:9:9" line-data="    @wire(getRecord, { recordId: &#39;$recordId&#39;, fields: PROPERTY_FIELDS })">`recordId`</SwmToken> and retrieve specific fields such as <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="5:2:2" line-data="import BROKER_FIELD from &#39;@salesforce/schema/Property__c.Broker__c&#39;;">`BROKER_FIELD`</SwmToken>.

```javascript
    @wire(getRecord, { recordId: '$recordId', fields: PROPERTY_FIELDS })
    property;
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
