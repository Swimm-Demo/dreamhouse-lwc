---
title: Introduction to City in Property Management
---
# Characteristics of the City Field

# Introduction to City in Property Management

City refers to the field used to store the city name associated with a property. This field is essential for categorizing and managing properties based on their geographical location.

# Usage of the City Field

The City field is a text field with a maximum length of 50 characters. It is not a required field, meaning that properties can be listed without specifying a city.

# Example Usage of City

The City field is utilized in various parts of the application, including property listings and tests. This ensures that properties can be filtered and displayed based on their city.

<SwmSnippet path="/force-app/main/default/lwc/propertyTile/__tests__/propertyTile.small.test.js" line="6">

---

An example of the City field being used can be found in the property listings and tests. For instance, in the file <SwmPath>[force-app/main/default/lwc/propertyTile/\__tests_\_/propertyTile.small.test.js](force-app/main/default/lwc/propertyTile/__tests__/propertyTile.small.test.js)</SwmPath>, the City field is referenced to ensure that properties are correctly associated with their respective cities.

```javascript
    City__c: 'Some City',
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
