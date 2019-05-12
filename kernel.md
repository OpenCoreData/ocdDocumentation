# Digital Object  (byte stream) properties

## About

A review of potential approaches to describing the properties for a type of digital object.  Here a DO is a simple byte stream.  It could be a zip, jpeg, PDF or CSV.    A DO might also be a formal package description like a Frictionless Data Package package.json manifest document that itself is made up of a set of DOs by reference.

## Different kernels

There are a few different sources we are looking at that could provide guidance on how to describe the small metadatsa kernel for a DO.  Note this is just a small set of elements for an object and not intended to describe a single instance or collection of objects that might form a dataset and be more easily described by schema:DataSet or DCAT:DataSet. 

So while a single DO might be used to define a data set as defined by schema.org/DataSet or DCAT, we want that to be a new object distinct from the byte stream DO.  If that is acceptable, then we need to define a small bit of core metadata to associate with a DO.   It's also felt that the presence of spatial, temporal, measurement or other metadata would be scoped into the dataset that a DO is a member of (represented by a new object) and not the DO itself.   The DO is simply the byte stream.  

References reviewed:

* Frictionless Data Packages (resource node) <https://frictionlessdata.io/specs/data-resource/>   Here we are looking only at data-resource as an object that would itself or with other objects be referenced by a full package.
* PID Kernel WG RDA <https://www.rd-alliance.org/groups/pid-kernel-information-wg> Though focused on PIDs there seems some value in considering this kernel and its potential use with digital objects.
* DID or Decentralized Identifiers <https://w3c-ccg.github.io/did-spec/>  is  about self sovereign digital identifiers.  So again more focused on PIDs but now in a decentralized manner.  Still, again this seems to have enough connection to digital objects to merit review.
* Schema.org type DigitalDocument <https://schema.org/DigitalDocument> is looking for something than be associated with a digital object as opposed to a data set or catalog.  
* DCAT-2 <https://w3c.github.io/dxwg/dcat/> This section needs attention.  Can we leverage DCAT to describe a DO/byte stream as opposed to a data set or catalog as differentiated in the above text. 

Note:  No attempt has been made to order these across the rows... that needs to be done

| FDP (resource) | PID                      | DID                      | schema.org                      | DCAT-2 |
| --------------------- | ------------------------ | ------------------------ | ------------------------------- | ------ |
| name                  | pid                      | id                       | schema:DigitalDocument          |        |
| path                  | KernelInformationProfile | publicKey                | schema:name                     |        |
| title                 | digitalObjectType        | authentication           | schema:URL                      |        |
| description           | digitalObjectLocation    | services                 | schema:about                    |        |
| format                | digitalObjectPolicy      | service:id               | schema:description              |        |
| mediatype             | etag                     | services:type            | schema:encodingFormat           |        |
| encoding              | dateModified             | services:serviceEndpoint | schema:fileSize                 |        |
| bytes                 | dateCreated              |                          | schema:identifier <br />(via PropVal, see below) |        |
| hash                  | version                  |                          | schema:isBasedOn                |        |
| schema                | wasDerivedFrom           |                          | schema:license                  |        |
| sources               | specialixationOF         |                          | schema:dateModified             |        |
| license               | wasRevisionOF            |                          | schema:dateCreated              |        |
|                       | hasPrimarySource         |                          | xyz:Type (domain typing)     |        |
|                       | wasQuotedFrom            |                          |                                 |        |
|                       | alternatOF               |                          |                                 |        |



This is an example of the current schema:DigitalDocument package we are generating

```JSON
{
  "@graph": [
    {
      "@id": "_:bbj6s49vtr9b9lop9n40g",
      "@type": "http://schema.org/PropertyValue",
      "http://schema.org/propertyID": "SHA256",
      "http://schema.org/value": "e88c1fa53004f75e2f1a761284c42e22d69e1750e70904c02c0b726ff42250ad"
    },
    {
      "@id": "http://opencoredata.org/id/do/bj6s49vtr9b9lop9n40g",
      "@type": "http://www.schema.org/DigitalDocument",
      "http://schema.org/additionType": {
        "@id": "http://opencoredata.org/voc/csdco/v1/ICDFiles"
      },
      "http://schema.org/dateCreated": "2009-11-02",
      "http://schema.org/description": "Digital object of type ICD named YNP3-ABD09-1A-1L-1.pdf for CSDCO project YNP3",
      "http://schema.org/encodingFormat": "application/pdf",
      "http://schema.org/identifier": {
        "@id": "_:bbj6s49vtr9b9lop9n40g"
      },
      "http://schema.org/isRelatedTo": "YNP3",
      "http://schema.org/license": {
        "@id": "http://example.com/cc0.html"
      },
      "http://schema.org/name": "YNP3-ABD09-1A-1L-1.pdf",
      "http://schema.org/url": {
        "@id": "http://opencoredata.org/id/do/e88c1fa53004f75e2f1a761284c42e22d69e1750e70904c02c0b726ff42250ad"
      }
    }
  ],
  "@id": "http://opencoredata.org/objectgraph/id/e88c1fa53004f75e2f1a761284c42e22d69e1750e70904c02c0b726ff42250ad"
}
```






<https://schema.org/identifier>  example pattern example

```json
{
 "@context": "http://schema.org/",
 "@type": "LocalBusiness",
 "name": "A UK Organization Ltd",
 "address": "1 A Street, London"
 "identifier": {
 "@type": "PropertyValue",
   "propertyID": "Company Number",
   "value":  "99065782"
   },
}
```

