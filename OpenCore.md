# Open Core Data Documentation 

## About

This is the start of the Open Core Data documnetation.   The goal is to provide a 
set of documents addressing:

* the use of Open Core Data by scientist
* an architecture overview to facilitate discussion among other geoinformatics professionals
* sufficient documentation to allow others to operate and administer the Open Core Data domain and applications. 

The document will evolve and split to facilitate these goal.  At present this document is a first version 
addressing the use of [opencoredata.org](http://opencoredata.org).  An [architecture](./Architecture.md) document 
is also under development to expose of the approaches being used.  Later an administration document will likely
split out of the architecture file. 


## RE3 citation
If you need to reference Open Core Data you can do so using the 
RE3Data DOI: http://doi.org/10.17616/R37936 

[Open Core Data RE3](http://service.re3data.org/repository/r3d100012071)

Citation:

```
re3data.org: Open Core Data; editing status 2016-07-27; 
re3data.org - Registry of Research Data Repositories. 
http://doi.org/10.17616/R37936 last accessed: 2016-08-25
```


## OutReach Events
Open Core Data is present at as many events as possible.  Below is a revese chronological order list with
future events at the top.  Please feel free to reach out to arrange getting together at these or other 
events. 

* AGU Fall meeting SF Dec 2016 
```
Abstract ID and Title: 186461: Open Core Data: Connecting scientific drilling 
data to scientists and community data resources 
Final Paper Number: IN53C-1898 
Presentation Type: Poster 
Session Date and Time: Friday, 16 December 2016; 13:40 - 18:00 
Session Number and Title: IN53C: Innovative Tools and Services to Enable Data Use 
across Broad User Communities II Posters 
Location: Moscone South; Poster Hall
```
* CSDCO Science Meeting Hilton Arlington Arlington, Virginia Washington D.C. Nov 13-14 2016
* LacCore Developer meeting Madison Wisonsin  Nov 3-4 2016 
* LacCore drilling institute June 13-24 and August 9-19 2016
* ESIP Summer meeting July 19-22 2016 Chapel Hill, NC
* EarthCube All Hands  July 6-8 2016 Denver Colorado
* Linked Earth meeting June 22-23 Denver Colorado
* C4P Hackathon  June 20-21 Denver Colorado

## Community connections

In order to enhance the impact of scientific drilling and core data, opencoredata.org 
will work with domain-specific data management efforts to ensure that drilling results
can be easily discovered and harvested by these external systems. This will allow 
specific subsets of IODP and CSDCO data (e.g. paleobiology, geochemistry, sedimentology, 
paleomagnetics, etc.) to gain visibility in domain-specific data systems serving 
their communities of scientists, including many who are not traditional users of 
drilling data, and integrate the results of scientific drilling projects with relevant 
related data for enhanced analysis and cross-disciplinary research.

Diary of interaction with the following groups:

* [Fly Over Country](http://fc.umn.edu/)  Open Core is working with FC developers to 
incorporate data holdings into this popular iOS and Android app.  Several APIs have 
been developed to expose metadata, links and abstract information for this app.  These 
APIs are documented along with all other Open Core APIs at the
[Open Core Swagger docs](http://opencoredata.org/common/swagger-ui/)

* [Neotoma](http://neotomadb.org/)  Open Core Data is working with Neotoma as an example how 
to improve the flow of data from facilities to community data portals like MagIC. 
Neotoma Paleoecology Database and Community is an online hub for data, research, education, 
and discussion about paleoenvironments. Anyone with an Internet connection can access Neotoma.

* [Gplates](http://portal.gplates.org/)


* [GeoLink](http://www.geolink.org/)  Open Core has a close connection with GeoLink.  
Many of the RDF based resources are connected to GeoLink ontology classes.

* [Magic](https://earthref.org/MagIC/)  Open Core Data is working with MagIC as an example 
how to improve the flow of magnetics data from facilities to community data portals like 
MagIC. MagIC is focused on promoting information technology infrastructures for the 
international paleomagnetic, geomagnetic and rock magnetic community.

* [GeoDeepDive](https://geodeepdive.org/)

## Citation

## Provenance 
Discussions with Hook Hau, Adam Leadbetter and other related to the 
development of provenance data for data have lead to some test using 
the PROV_ES patterns (ref: http://pymonger.github.io/prov_es/index.html) 
some intial testing using this library (https://gist.github.com/fils/f65feca2632dbdd86032 ) 
result in additional JSON-LD formated metadata that can be associated with datasets.  
This is potentially important as work is done to move data out of OCD and
 into groups like Neotoma and MagIC or others.   Elements of this work will 
 show up in ocdJans and ocdCSDCO to allow this metadata to be interconnected 
 with other metadata.  

## APIs

## Semantics & Vocabularies

Semantics is woven through the entire system providing the link structure for the 
LOD patterns and the connections into the GeoLink and other graphs.
Not mentioned to this point are the vocabulary files that help 
provide both meaning, context and discovery.  The example dataset 
landing page linked above and imaged here does not yet provide 
“description” information.  However, this information has been collected 
at: http://opencoredata.org/voc/janus/1/ocdJanusSKOS.ttl .  This is early 
version of this document that doesn’t yet have the full W3C patterned 
interface to the various elements. 
We have the information collected to expand this to include unit and unit 
description along with these terms.  We also have descriptions of the 
measurement and aggregation searches that will be included into a SKOS vocabulary.  
Future work will connect these with ODM2 developments. 


## Notebook development

## Formats for Data & Metadata

As noted there are several key patterns and standards (or recommendations) being used in OCD data. 
These include:
* Format: JSON-LD  (https://www.w3.org/TR/json-ld/ )
Used for both data (CSV for the Web guided) and metadata (schema.org)
* CSV for the Web (https://www.w3.org/2013/csvw/wiki/Main_Page )
Used for data and metadata (CSVW metadata format https://www.w3.org/TR/2015/REC-tabular-metadata-20151217/ )
    * Metadata example: http://opencoredata.org/api/v1/documents/download/1b50ee1d-536b-4490-9741-e1e2abc67750/CSVW 
    * Data example:  http://opencoredata.org/api/v1/documents/download/191_1179B_JanusNgrSection_oNUlnJFS.csv 
* Schema.org (http://schema.org/ ) 
Used for metadata with a focus on the Dataset element
Example:  http://opencoredata.org/api/v1/documents/download/1b50ee1d-536b-4490-9741-e1e2abc67750/JSON 


Metadata is also generated using the GeoLink vocabulary and is exposed following GeoLink 
harvesting guidelines.  Though the creation of LiPD metadata is not part of this phase LiPD 
uses the JSON-LD format and closely follows the CSVW approach.  Elements have been put 
in place already to support creating LiPD documents 

Several of these example links came from the data landing page at:  
http://opencoredata.org/doc/dataset/1b50ee1d-536b-4490-9741-e1e2abc67750 

