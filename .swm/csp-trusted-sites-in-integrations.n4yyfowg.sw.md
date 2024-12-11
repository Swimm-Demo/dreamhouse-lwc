---
title: CSP Trusted Sites in Integrations
---
# What is CSP Trusted Sites

CSP Trusted Sites are configurations that specify which external sites are trusted to load certain types of content within the application.

# How CSP Trusted Sites are Used

These configurations ensure that only content from trusted sources is allowed, enhancing the security of the application.

<SwmSnippet path="/force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml" line="1">

---

For example, the file <SwmPath>[force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml](force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml)</SwmPath> specifies that content from <SwmToken path="force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml" pos="7:4:16" line-data="    &lt;endpointUrl&gt;https://s3-us-west-2.amazonaws.com&lt;/endpointUrl&gt;">`https://s3-us-west-2.amazonaws.com`</SwmToken> is trusted for image sources.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CspTrustedSite xmlns="http://soap.sforce.com/2006/04/metadata">
    <canAccessCamera>false</canAccessCamera>
    <canAccessMicrophone>false</canAccessMicrophone>
    <context>LEX</context>
    <description>Amazon S3 hosted sample app media</description>
    <endpointUrl>https://s3-us-west-2.amazonaws.com</endpointUrl>
    <isActive>true</isActive>
    <isApplicableToConnectSrc>false</isApplicableToConnectSrc>
    <isApplicableToFontSrc>false</isApplicableToFontSrc>
    <isApplicableToFrameSrc>false</isApplicableToFrameSrc>
    <isApplicableToImgSrc>true</isApplicableToImgSrc>
    <isApplicableToMediaSrc>false</isApplicableToMediaSrc>
    <isApplicableToStyleSrc>false</isApplicableToStyleSrc>
</CspTrustedSite>
```

---

</SwmSnippet>

<SwmSnippet path="/force-app/main/default/cspTrustedSites/openStreetMap.cspTrustedSite-meta.xml" line="1">

---

Similarly, the file <SwmPath>[force-app/main/default/cspTrustedSites/openStreetMap.cspTrustedSite-meta.xml](force-app/main/default/cspTrustedSites/openStreetMap.cspTrustedSite-meta.xml)</SwmPath> indicates that content from <SwmToken path="force-app/main/default/cspTrustedSites/openStreetMap.cspTrustedSite-meta.xml" pos="7:4:10" line-data="    &lt;endpointUrl&gt;https://tile.openstreetmap.org&lt;/endpointUrl&gt;">`https://tile.openstreetmap.org`</SwmToken> is trusted for image sources.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CspTrustedSite xmlns="http://soap.sforce.com/2006/04/metadata">
    <canAccessCamera>false</canAccessCamera>
    <canAccessMicrophone>false</canAccessMicrophone>
    <context>LEX</context>
    <description>OpenStreetMap tiles</description>
    <endpointUrl>https://tile.openstreetmap.org</endpointUrl>
    <isActive>true</isActive>
    <isApplicableToConnectSrc>false</isApplicableToConnectSrc>
    <isApplicableToFontSrc>false</isApplicableToFontSrc>
    <isApplicableToFrameSrc>false</isApplicableToFrameSrc>
    <isApplicableToImgSrc>true</isApplicableToImgSrc>
    <isApplicableToMediaSrc>false</isApplicableToMediaSrc>
    <isApplicableToStyleSrc>false</isApplicableToStyleSrc>
</CspTrustedSite>
```

---

</SwmSnippet>

## Specifying Trusted External Sites

# Main Functions

There are several main functions in CSP Trusted Sites. Some of them are specifying trusted external sites and enhancing application security. We will dive a little into these functions.

<SwmSnippet path="/force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml" line="1">

---

CSP Trusted Sites are configurations that specify which external sites are trusted to load certain types of content within the application. For example, the file <SwmPath>[force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml](force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml)</SwmPath> specifies that content from <SwmToken path="force-app/main/default/cspTrustedSites/s3_us_west_2_amazonaws_com.cspTrustedSite-meta.xml" pos="7:4:16" line-data="    &lt;endpointUrl&gt;https://s3-us-west-2.amazonaws.com&lt;/endpointUrl&gt;">`https://s3-us-west-2.amazonaws.com`</SwmToken> is trusted for image sources.

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<CspTrustedSite xmlns="http://soap.sforce.com/2006/04/metadata">
    <canAccessCamera>false</canAccessCamera>
    <canAccessMicrophone>false</canAccessMicrophone>
    <context>LEX</context>
    <description>Amazon S3 hosted sample app media</description>
    <endpointUrl>https://s3-us-west-2.amazonaws.com</endpointUrl>
    <isActive>true</isActive>
    <isApplicableToConnectSrc>false</isApplicableToConnectSrc>
    <isApplicableToFontSrc>false</isApplicableToFontSrc>
    <isApplicableToFrameSrc>false</isApplicableToFrameSrc>
    <isApplicableToImgSrc>true</isApplicableToImgSrc>
    <isApplicableToMediaSrc>false</isApplicableToMediaSrc>
    <isApplicableToStyleSrc>false</isApplicableToStyleSrc>
</CspTrustedSite>
```

---

</SwmSnippet>

&nbsp;

*This is an auto-generated document by Swimm 🌊 and has not yet been verified by a human*

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBZHJlYW1ob3VzZS1sd2MlM0ElM0FTd2ltbS1EZW1v" repo-name="dreamhouse-lwc"><sup>Powered by [Swimm](/)</sup></SwmMeta>
