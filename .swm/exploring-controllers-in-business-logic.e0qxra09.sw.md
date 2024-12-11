---
title: Exploring Controllers in Business Logic
---
# <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="1:8:8" line-data="public with sharing class PropertyController {">`PropertyController`</SwmToken>

# Overview

Controllers are classes that handle the business logic of the application. They are responsible for processing incoming requests, interacting with the data model, and returning the appropriate responses.

## <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="16:7:7" line-data="    public static PagedResult getPagedPropertyList(">`getPagedPropertyList`</SwmToken>

The <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="1:8:8" line-data="public with sharing class PropertyController {">`PropertyController`</SwmToken> class is a key component in managing property-related operations. It includes methods for retrieving property lists and associated pictures.

<SwmSnippet path="/force-app/main/default/classes/PropertyController.cls" line="1">

---

The <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="16:7:7" line-data="    public static PagedResult getPagedPropertyList(">`getPagedPropertyList`</SwmToken> method retrieves a paged and filtered list of properties based on various search criteria such as property title, city, tags, maximum price, minimum number of bedrooms, and bathrooms. This method normalizes the input parameters, constructs a search pattern, calculates the offset for pagination, and queries the <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="5:10:10" line-data="        delete [SELECT Id FROM Property__c];">`Property__c`</SwmToken> object to get the total item count and the list of properties matching the criteria.

```apex
public with sharing class PropertyController {
    private static final Decimal DEFAULT_MAX_PRICE = 9999999;
    private static final Integer DEFAULT_PAGE_SIZE = 9;

    /**
     * Endpoint that retrieves a paged and filtered list of properties
     * @param searchKey String used for searching on property title, city and tags
     * @param maxPrice Maximum price
     * @param minBedrooms Minimum number of bedrooms
     * @param minBathrooms Minimum number of bathrooms
     * @param pageSize Number of properties per page
     * @param pageNumber Page number
     * @return PagedResult object holding the paged and filtered list of properties
     */
    @AuraEnabled(cacheable=true scope='global')
    public static PagedResult getPagedPropertyList(
        String searchKey,
        Decimal maxPrice,
        Integer minBedrooms,
        Integer minBathrooms,
        Integer pageSize,
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/classes/PropertyController.cls" line="78">

---

## <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="84:10:10" line-data="    public static List&lt;ContentVersion&gt; getPictures(Id propertyId) {">`getPictures`</SwmToken>

The <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="84:10:10" line-data="    public static List&lt;ContentVersion&gt; getPictures(Id propertyId) {">`getPictures`</SwmToken> method retrieves pictures associated with a specific property. This method queries the <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="85:3:3" line-data="        List&lt;ContentDocumentLink&gt; links = [">`ContentDocumentLink`</SwmToken> object to find links to content documents related to the property and then retrieves the latest versions of these documents from the <SwmToken path="force-app/main/default/classes/PropertyController.cls" pos="81:10:10" line-data="     * @return List of ContentVersion holding the pictures">`ContentVersion`</SwmToken> object.

```apex
    /**
     * Endpoint that retrieves pictures associated with a property
     * @param propertyId Property Id
     * @return List of ContentVersion holding the pictures
     */
    @AuraEnabled(cacheable=true scope='global')
    public static List<ContentVersion> getPictures(Id propertyId) {
        List<ContentDocumentLink> links = [
            SELECT Id, LinkedEntityId, ContentDocument.Title
            FROM ContentDocumentLink
            WHERE
                LinkedEntityId = :propertyId
                AND ContentDocument.FileType IN ('PNG', 'JPG', 'GIF')
            WITH USER_MODE
        ];

        if (links.isEmpty()) {
            return null;
        }

        Set<Id> contentIds = new Set<Id>();
```

---

</SwmSnippet>

## <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="3:7:7" line-data="    public static void importSampleData() {">`importSampleData`</SwmToken>

# <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="1:8:8" line-data="public with sharing class SampleDataController {">`SampleDataController`</SwmToken>

The <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="1:8:8" line-data="public with sharing class SampleDataController {">`SampleDataController`</SwmToken> class is used to import sample data into the application. It includes methods for deleting existing records and inserting new sample data.

<SwmSnippet path="/force-app/main/default/classes/SampleDataController.cls" line="1">

---

The <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="3:7:7" line-data="    public static void importSampleData() {">`importSampleData`</SwmToken> method deletes existing records from several objects such as <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="4:10:10" line-data="        delete [SELECT Id FROM Case];">`Case`</SwmToken>, <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="5:10:10" line-data="        delete [SELECT Id FROM Property__c];">`Property__c`</SwmToken>, <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="6:10:10" line-data="        delete [SELECT Id FROM Broker__c];">`Broker__c`</SwmToken>, and <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="7:10:10" line-data="        delete [SELECT Id FROM Contact];">`Contact`</SwmToken>, and then inserts new sample data into these objects. This method calls private helper methods like <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="9:1:1" line-data="        insertBrokers();">`insertBrokers`</SwmToken>, <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="10:1:1" line-data="        insertProperties();">`insertProperties`</SwmToken>, and <SwmToken path="force-app/main/default/classes/SampleDataController.cls" pos="11:1:1" line-data="        insertContacts();">`insertContacts`</SwmToken> to handle the insertion of sample data for brokers, properties, and contacts respectively.

```apex
public with sharing class SampleDataController {
    @AuraEnabled
    public static void importSampleData() {
        delete [SELECT Id FROM Case];
        delete [SELECT Id FROM Property__c];
        delete [SELECT Id FROM Broker__c];
        delete [SELECT Id FROM Contact];

        insertBrokers();
        insertProperties();
        insertContacts();
    }

    private static void insertBrokers() {
        StaticResource brokersResource = [
            SELECT Id, Body
            FROM StaticResource
            WHERE Name = 'sample_data_brokers'
        ];
        String brokersJSON = brokersResource.body.toString();
        List<Broker__c> brokers = (List<Broker__c>) JSON.deserialize(
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
