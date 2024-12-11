---
title: Introduction to Business Logic Utilities
---
## <SwmToken path="force-app/main/default/classes/FileUtilities.cls" pos="1:8:8" line-data="public with sharing class FileUtilities {">`FileUtilities`</SwmToken>

# Introduction

Utilities in Business Logic refer to helper classes and methods that provide common functionalities used across the application. These utilities are designed to perform specific tasks that are needed in multiple places, thereby promoting code reusability and reducing redundancy.

<SwmSnippet path="/force-app/main/default/classes/FileUtilities.cls" line="1">

---

The <SwmToken path="force-app/main/default/classes/FileUtilities.cls" pos="1:8:8" line-data="public with sharing class FileUtilities {">`FileUtilities`</SwmToken> class contains methods for handling file operations, such as creating files from base64 data and linking them to specific records. This class encapsulates the logic required to manage files, making it easier to maintain and update file-related functionalities.

```apex
public with sharing class FileUtilities {
    @AuraEnabled
    public static String createFile(
        String base64data,
        String filename,
        String recordId
    ) {
        try {
            ContentVersion contentVersion = new ContentVersion();
            contentVersion.VersionData = EncodingUtil.base64Decode(base64data);
            contentVersion.Title = filename;
            contentVersion.PathOnClient = filename;
            insert contentVersion;

            contentVersion = [
                SELECT ContentDocumentId
                FROM ContentVersion
                WHERE Id = :contentVersion.Id
                WITH USER_MODE
            ];

```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/classes/PagedResult.cls" line="1">

---

## <SwmToken path="force-app/main/default/classes/PagedResult.cls" pos="1:8:8" line-data="public with sharing class PagedResult {">`PagedResult`</SwmToken>

Another utility class is <SwmToken path="force-app/main/default/classes/PagedResult.cls" pos="1:8:8" line-data="public with sharing class PagedResult {">`PagedResult`</SwmToken>, which is used to handle pagination of data. It includes properties and methods to manage the size of pages, the current page number, the total item count, and the records to be displayed. This utility simplifies the process of implementing pagination in the application.

```apex
public with sharing class PagedResult {
    @AuraEnabled
    public Integer pageSize { get; set; }

    @AuraEnabled
    public Integer pageNumber { get; set; }

    @AuraEnabled
    public Integer totalItemCount { get; set; }

    @AuraEnabled
    public Object[] records { get; set; }
}
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/errorPanel/errorPanel.js" line="2">

---

## <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="2:4:4" line-data="import { reduceErrors } from &#39;c/ldsUtils&#39;;">`reduceErrors`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="2:4:4" line-data="import { reduceErrors } from &#39;c/ldsUtils&#39;;">`reduceErrors`</SwmToken> function is used to process and simplify error messages. It takes an array of errors and returns a more <SwmToken path="force-app/main/default/lwc/errorPanel/errorPanel.js" pos="9:7:9" line-data="    /** Generic / user-friendly message */">`user-friendly`</SwmToken> message.

```javascript
import { reduceErrors } from 'c/ldsUtils';
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/lwc/propertyMap/propertyMap.js" line="2">

---

## <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="2:4:4" line-data="import { getRecord } from &#39;lightning/uiRecordApi&#39;;">`getRecord`</SwmToken>

The <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="2:4:4" line-data="import { getRecord } from &#39;lightning/uiRecordApi&#39;;">`getRecord`</SwmToken> function is used to retrieve a record from the Salesforce database. It is commonly used with the <SwmToken path="force-app/main/default/lwc/propertyMap/propertyMap.js" pos="26:1:2" line-data="    @wire(MessageContext)">`@wire`</SwmToken> decorator to fetch data and bind it to a component.

```javascript
import { getRecord } from 'lightning/uiRecordApi';
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
