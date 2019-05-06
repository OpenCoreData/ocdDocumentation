# Open Care Data Architecture

### Overview 
Open Core Data is almost entirely built on Go (server side) and JS client side with the 
use of Polymer web components mixed in.  All the code except for some of the database server
set up and some utility code is present at the GitHub repository.
 [Open Core GitHub](https://github.com/OpenCoreData)

### Elements
More details will be added, but some key approaches include:

* Use of Go lang
* Docker:  All elements of OCD are in docker containers.  Movement of the OCD system to another
docker environment is trivial.  A Docker compose file is also udner development to allow a 1 file
deployment of all elements other than the large data volumes.  Those data volumes are many terrabtyes
in size.
* http 2.0 + SSL:  Really http 2.0 implies SSL but it's perhaps good to be explicate.  
* Semantics including community onotlogies like GeoLink and also Linked Open Data (LOD) patterns
* APIs defined by swagger documentation

### Git repositories
https://github.com/OpenCoreData

### Other

##### Web Components

A set of web components is being developed as part of the GeoLink effort.  These web component have
direct use in OCD and also demonstrate an approach that will make the maintenance of the web
interface easier in the future by allow a “modular approach” to the pages.  Work on components
can be found at [https://github.com/glcomponents ](https://github.com/glcomponents )
and [GeoLink Components catalog](http://glcomponents.tech/catalogue.html).

##### Persistant Identifies
More details will follow but the follow are already in the work flow

* RE3Data:  Open Core Data has a RE3Data DOI assigned to it
* DOIs:  Data resources will soon get DOIs via EZID with Datacite 4.0 metadata.  Note at this time
the EZID API does not support version 4 of the Datacite kernel.
* Orcids:  Processes for the use of Oricids is under discussion with the data facilities. 
[ref 1](http://orcid.org/content/requiring-orcid-publication-workflows-open-letter)


##### Data publishing notes
A collection of notes to review on data publishing approaches.

Need to review http://www.copdess.org/ COPDESS and also the EC Council of Data Facilities.  
Also the ESIP Fed data publishing guidelines.  
Look over http://wiki.tdwg.org/twiki/bin/view/DarwinCore/PaleontologyElement (Paleo Darwin 
Core, ADBC, etc)  (there is no paleo extension anymore..  it’s part of the core)
BCO (https://github.com/tucotuco/bco) and DarwinCore have a very similar relation to each 
other as the ODP’s and Views have in GeoLink.   
Focus on the sample (thing) with IGSN and the metadata with that.  Then hang your data off 
that with simple URI’s.


##### Future outreach intentions
There are more groups to contemplate interaction with than there is time. So care must
be used in the selction of partners.  That said, there are many groups like the following
that should be evaluated for work with.

DCO  
https://deepcarbon.net/

Keck GeoBioSphere  
https://dtdi.carnegiescience.edu/about  