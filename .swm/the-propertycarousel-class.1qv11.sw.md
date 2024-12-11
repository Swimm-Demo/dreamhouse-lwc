---
title: The PropertyCarousel class
---
This document will cover the class <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken>. We will explain:

1. What <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken> is.
2. The variables and functions defined in <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken>.

# Variables and functions

# What is <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken>

<SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken> is a Lightning Web Component (LWC) defined in the file <SwmPath>[force-app/main/default/lwc/propertyCarousel/propertyCarousel.js](force-app/main/default/lwc/propertyCarousel/propertyCarousel.js)</SwmPath>. It is used to display a carousel of property images for a given property record in Salesforce. The component fetches property details and associated images, processes the images, and displays them in a carousel format.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="23">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="23:1:1" line-data="    wiredPictures(pictures) {">`wiredPictures`</SwmToken> is a wired function that fetches pictures associated with the property. It processes the fetched pictures and maps them to carousel items.

```javascript
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

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="40">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="40:3:3" line-data="    get address() {">`address`</SwmToken> is a getter that retrieves the address field value from the property record.

```javascript
    get address() {
        return getFieldValue(this.property.data, ADDRESS_FIELD);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="44">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="44:3:3" line-data="    get city() {">`city`</SwmToken> is a getter that retrieves the city field value from the property record.

```javascript
    get city() {
        return getFieldValue(this.property.data, CITY_FIELD);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="48">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="48:3:3" line-data="    get description() {">`description`</SwmToken> is a getter that retrieves the description field value from the property record.

```javascript
    get description() {
        return getFieldValue(this.property.data, DESCRIPTION_FIELD);
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="52">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="52:3:3" line-data="    get errors() {">`errors`</SwmToken> is a getter that collects and returns any errors encountered while fetching the property or pictures.

```javascript
    get errors() {
        const errors = [this.property.error, this.pictures.error].filter(
            (error) => error
        );
        return errors.length ? errors : null;
    }
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="61">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="61:3:3" line-data="    async handleFilesSelected(event) {">`handleFilesSelected`</SwmToken> is an asynchronous function that handles file selection, processes the selected images, and uploads them to the server.

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

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" line="98">

---

The function <SwmToken path="force-app/main/default/lwc/propertyCarousel/propertyCarousel.js" pos="98:3:3" line-data="    async blobToBase64(blob) {">`blobToBase64`</SwmToken> is an asynchronous function that converts a Blob object to a Base64 encoded string.

```javascript
    async blobToBase64(blob) {
        return new Promise((resolve) => {
            const reader = new FileReader();
            reader.onloadend = () => resolve(reader.result.split(',')[1]); // Remove Data-URL declaration
            reader.readAsDataURL(blob);
        });
    }
```

---

</SwmSnippet>

# Usage

## <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken> in Tests

The <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="58:4:4" line-data="                is: PropertyCarousel">`PropertyCarousel`</SwmToken> class is used in various test cases to verify its functionality. For instance, it is instantiated and appended to the document body to test different scenarios.

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" line="55">

---

One example is testing if the carousel renders with pictures when both property and pictures are returned. This ensures that the component correctly displays the images associated with a property.

```javascript
    describe('@wire data', () => {
        it('renders carousel with pictures when property and pictures returned', async () => {
            const element = createElement('c-property-carousel', {
                is: PropertyCarousel
            });
            document.body.appendChild(element);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" line="80">

---

Another test case checks if the component renders a message indicating no pictures are available when a property is returned without pictures. This helps verify the component's behavior in the absence of images.

```javascript
        it('renders no pictures message when property but no pictures returned', async () => {
            const element = createElement('c-property-carousel', {
                is: PropertyCarousel
            });
            document.body.appendChild(element);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" line="104">

---

Additionally, there are tests to ensure the component handles errors gracefully. For example, one test verifies that an error message is rendered when the <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="104:10:10" line-data="        it(&#39;renders error when getProperty returns error&#39;, async () =&gt; {">`getProperty`</SwmToken> method returns an error.

```javascript
        it('renders error when getProperty returns error', async () => {
            const element = createElement('c-property-carousel', {
                is: PropertyCarousel
            });
            document.body.appendChild(element);
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" line="121">

---

Similarly, another test checks if an error message is displayed when the <SwmToken path="force-app/main/default/lwc/propertyCarousel/__tests__/propertyCarousel.test.js" pos="121:10:10" line-data="        it(&#39;renders error when getPictures returns error&#39;, async () =&gt; {">`getPictures`</SwmToken> method encounters an error. This ensures that the component can handle and display errors appropriately.

```javascript
        it('renders error when getPictures returns error', async () => {
            const element = createElement('c-property-carousel', {
                is: PropertyCarousel
            });
            document.body.appendChild(element);
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
