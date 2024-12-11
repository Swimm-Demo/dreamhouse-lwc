---
title: The BarcodeScanner class
---
This document will cover the <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken> class. We will explain:

1. What <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken> is.
2. The variables and functions defined in <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken>.

## <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="12:1:1" line-data="    connectedCallback() {">`connectedCallback`</SwmToken>

# What is <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken> class in <SwmPath>[force-app/main/default/lwc/barcodeScanner/barcodeScanner.js](force-app/main/default/lwc/barcodeScanner/barcodeScanner.js)</SwmPath> is a Lightning Web Component (LWC) that provides functionality to scan QR codes using a mobile device's camera. It is used to capture QR code data and navigate to a specific record page based on the scanned data.

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="12">

---

The function <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="12:1:1" line-data="    connectedCallback() {">`connectedCallback`</SwmToken> is a lifecycle hook in the <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="23:7:7" line-data="        // Make sure BarcodeScanner is available before trying to use it">`BarcodeScanner`</SwmToken> class. It initializes the barcode scanner and determines whether the scan button should be enabled.

```javascript
    connectedCallback() {
        this.myScanner = getBarcodeScanner();
        if (this.myScanner?.isAvailable()) {
            this.scanButtonEnabled = true;
        }
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="19">

---

## <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="19:3:3" line-data="    async handleBeginScanClick() {">`handleBeginScanClick`</SwmToken>

The function <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="19:3:3" line-data="    async handleBeginScanClick() {">`handleBeginScanClick`</SwmToken> is an asynchronous function that handles the click event for starting a QR code scan. It resets the scanned QR code, checks if the scanner is available, and initiates the scanning process.

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

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="7">

---

The variable <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="7:1:1" line-data="    myScanner;">`myScanner`</SwmToken> is used to store the instance of the barcode scanner.

```javascript
    myScanner;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="8">

---

The variable <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="8:1:1" line-data="    scanButtonEnabled = false;">`scanButtonEnabled`</SwmToken> is a boolean that indicates whether the scan button should be enabled.

```javascript
    scanButtonEnabled = false;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" line="9">

---

The variable <SwmToken path="force-app/main/default/lwc/barcodeScanner/barcodeScanner.js" pos="9:1:1" line-data="    scannedQrCode = &#39;&#39;;">`scannedQrCode`</SwmToken> is used to store the value of the scanned QR code.

```javascript
    scannedQrCode = '';
```

---

</SwmSnippet>

# Usage

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" line="36">

---

## <SwmPath>[force-app/main/default/lwc/barcodeScanner/\__tests_\_/barcodeScanner.test.js](force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js)</SwmPath>

In the <SwmPath>[force-app/main/default/lwc/barcodeScanner/\__tests_\_/barcodeScanner.test.js](force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js)</SwmPath> file, the <SwmToken path="force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" pos="37:7:7" line-data="        // Create initial BarcodeScanner element and attach to virtual DOM">`BarcodeScanner`</SwmToken> class is used to create an initial <SwmToken path="force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" pos="37:7:7" line-data="        // Create initial BarcodeScanner element and attach to virtual DOM">`BarcodeScanner`</SwmToken> element and attach it to the virtual DOM. This is demonstrated in the test case where it directs the user to the mobile app when the Barcode Scanner is unavailable.

```javascript
    it('directs the user to the mobile app when Barcode Scanner is unavailable', async () => {
        // Create initial BarcodeScanner element and attach to virtual DOM
        const elementBarcodeScanner = createElement(
            'c-barcode-scanner-example',
            { is: BarcodeScanner }
        );
        document.body.appendChild(elementBarcodeScanner);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" line="53">

---

## <SwmPath>[force-app/main/default/lwc/barcodeScanner/\__tests_\_/barcodeScanner.test.js](force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js)</SwmPath>

Another usage example in the <SwmPath>[force-app/main/default/lwc/barcodeScanner/\__tests_\_/barcodeScanner.test.js](force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js)</SwmPath> file shows the <SwmToken path="force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" pos="53:9:13" line-data="    it(&#39;shows the `Scan QR Code` button when BarcodeScanner is available&#39;, async () =&gt; {">`Scan QR Code`</SwmToken> button when the Barcode Scanner is available. This involves creating an initial <SwmToken path="force-app/main/default/lwc/barcodeScanner/__tests__/barcodeScanner.test.js" pos="53:20:20" line-data="    it(&#39;shows the `Scan QR Code` button when BarcodeScanner is available&#39;, async () =&gt; {">`BarcodeScanner`</SwmToken> element and attaching it to the virtual DOM.

```javascript
    it('shows the `Scan QR Code` button when BarcodeScanner is available', async () => {
        // Create initial BarcodeScanner element and attach to virtual DOM
        const elementBarcodeScanner = createElement(
            'c-barcode-scanner-example',
            { is: BarcodeScanner }
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
