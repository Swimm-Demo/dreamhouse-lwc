---
title: Business Logic Overview
---
# Where Business Logic is Used

# What is Business Logic

Business logic refers to the part of the application that encodes the real-world business rules that determine how data can be created, stored, and changed.

# Implementation of Business Logic

Business logic is used to ensure that the data adheres to the specific rules and constraints of the business domain. It is implemented in classes that handle operations related to specific data, ensuring that the data follows the business rules.

# Examples of Business Logic

The business logic in this repository is implemented in the classes located in the <SwmPath>[force-app/main/default/classes/](force-app/main/default/classes/)</SwmPath> directory.

<SwmSnippet path="/force-app/main/default/classes/PropertyController.cls" line="1">

---

For instance, <SwmPath>[force-app/main/default/classes/PropertyController.cls](force-app/main/default/classes/PropertyController.cls)</SwmPath> contains methods that handle operations related to property data. These methods are responsible for creating, retrieving, updating, and deleting property records while ensuring that the operations adhere to the business rules defined within the application.

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
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/classes/SampleDataController.cls" line="1">

---

Similarly, <SwmPath>[force-app/main/default/classes/SampleDataController.cls](force-app/main/default/classes/SampleDataController.cls)</SwmPath> manages sample data operations. This class includes methods that generate and manipulate sample data, ensuring that the data conforms to the business rules and logic of the application.

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
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
