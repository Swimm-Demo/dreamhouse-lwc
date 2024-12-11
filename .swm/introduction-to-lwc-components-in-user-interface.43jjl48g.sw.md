---
title: Introduction to LWC Components in User Interface
---
# Introduction to LWC Components

LWC (Lightning Web Components) are the building blocks of the user interface in Salesforce. They are designed to create reusable and modular pieces of the UI, enhancing both development efficiency and code maintainability.

# Structure of LWC Components

These components are defined in the <SwmPath>[force-app/main/default/lwc/](force-app/main/default/lwc/)</SwmPath> directory. This directory includes various functionalities such as property filters, maps, and data importers, which are essential for building dynamic and interactive user interfaces.

Each LWC component typically consists of HTML, JavaScript, and metadata files. These files define the component's structure, behavior, and configuration, respectively.

<SwmSnippet path="/force-app/main/default/lwc/propertyFilter/propertyFilter.js" line="45">

---

For example, the `propertyFilter` component includes methods like <SwmToken path="force-app/main/default/lwc/propertyFilter/propertyFilter.js" pos="45:1:1" line-data="    fireChangeEvent() {">`fireChangeEvent`</SwmToken> to handle user interactions and update the UI accordingly.

```javascript
    fireChangeEvent() {
        // Debouncing this method: Do not actually fire the event as long as this function is
        // being called within a delay of DELAY. This is to avoid a very large number of Apex
        // method calls in components listening to this event.
        window.clearTimeout(this.delayTimeout);
        // eslint-disable-next-line @lwc/lwc/no-async-operation
        this.delayTimeout = setTimeout(() => {
            const filters = {
                searchKey: this.searchKey,
                maxPrice: this.maxPrice,
                minBedrooms: this.minBedrooms,
                minBathrooms: this.minBathrooms
            };
            publish(this.messageContext, FILTERSCHANGEMC, filters);
        }, DELAY);
    }
```

---

</SwmSnippet>

## Paginator Component

# Key Components and Their Functionalities

Different LWC components serve various purposes within the application. Below are some key components and their functionalities:

<SwmSnippet path="/force-app/main/default/lwc/paginator/paginator.js" line="6">

---

The <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="5:6:6" line-data="export default class Paginator extends LightningElement {">`Paginator`</SwmToken> component includes a <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="7:4:4" line-data="    @api pageNumber;">`pageNumber`</SwmToken> property, which represents the current page number. This property is defined using the <SwmToken path="force-app/main/default/lwc/paginator/paginator.js" pos="7:1:2" line-data="    @api pageNumber;">`@api`</SwmToken> decorator, making it accessible from outside the component.

```javascript
    /** The current page number. */
    @api pageNumber;
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/brokerCard/brokerCard.js" line="31">

---

## <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="19:6:6" line-data="export default class BrokerCard extends NavigationMixin(LightningElement) {">`BrokerCard`</SwmToken> Component

The <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="19:6:6" line-data="export default class BrokerCard extends NavigationMixin(LightningElement) {">`BrokerCard`</SwmToken> component includes a <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="31:1:1" line-data="    handleNavigateToRecord() {">`handleNavigateToRecord`</SwmToken> method. This public method navigates to a specific record page using the <SwmToken path="force-app/main/default/lwc/brokerCard/brokerCard.js" pos="32:3:3" line-data="        this[NavigationMixin.Navigate]({">`NavigationMixin`</SwmToken> to perform the navigation action.

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
