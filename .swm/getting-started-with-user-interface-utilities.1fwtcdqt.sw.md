---
title: Getting Started with User Interface Utilities
---
# Getting Started with User Interface Utilities

Utilities in the User Interface are helper functions and components designed to streamline common tasks and enhance the user experience.

They provide reusable code that can be leveraged across different parts of the application, ensuring consistency and reducing redundancy.

For example, the <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="2:13:13" line-data="import { reduceErrors } from &#39;c/ldsUtils&#39;;">`ldsUtils`</SwmToken> directory contains utility functions that facilitate interactions with the Lightning Data Service, making it easier to perform CRUD operations on Salesforce records.

## Utilities Endpoints

Additionally, the `navigateToRecord` component provides a utility to navigate to a specific record page, simplifying the process of linking to records within the application.

### <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="2:4:4" line-data="import { reduceErrors } from &#39;c/ldsUtils&#39;;">`reduceErrors`</SwmToken>

The repository includes several utility endpoints that are essential for various functionalities within the application.

<SwmSnippet path="/force-app/main/default/lwc/errorPanel/errorPanel.js" line="2">

---

The <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="2:4:4" line-data="import { reduceErrors } from &#39;c/ldsUtils&#39;;">`reduceErrors`</SwmToken> function is a utility that processes an array of errors and returns a simplified list of error messages. This function is particularly useful for displaying <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="9:7:9" line-data="    /** Generic / user-friendly message */">`user-friendly`</SwmToken> error messages in the UI.

```javascript
import { reduceErrors } from 'c/ldsUtils';
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/navigateToRecord/navigateToRecord.js" line="1">

---

### navigateToRecord

The `navigateToRecord` component provides a utility to navigate to a specific record page. It simplifies the process of linking to records within the application by using the <SwmToken path="force-app/main/default/lwc/navigateToRecord/navigateToRecord.js" pos="2:4:4" line-data="import { NavigationMixin } from &#39;lightning/navigation&#39;;">`NavigationMixin`</SwmToken> to handle the navigation logic.

```javascript
import { LightningElement, api } from 'lwc';
import { NavigationMixin } from 'lightning/navigation';

export default class NavigateToRecord extends NavigationMixin(
    LightningElement
) {
    @api recordId;

    connectedCallback() {
        this[NavigationMixin.Navigate]({
            type: 'standard__recordPage',
            attributes: {
                recordId: this.recordId,
                actionName: 'view'
            }
        });
    }
}
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
