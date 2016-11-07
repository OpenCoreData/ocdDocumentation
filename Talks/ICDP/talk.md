<!-- $theme: default -->
<!-- template: invert -->
<!-- footer: This document is at github.com/OpenCoreData/ocdDocuments/ -->

Open Core Data Status Update for ICDP
===
# ![](media/drillheads.jpg)
##### A review of Open Core Data [opencoredata.org](http://opencoredata.org)
###### Douglas Fils ( [@fils](https://twitter.com/fils) )
---
# Outline

- **Review of Architecture**
	- Docker based
	- Simple dependancy approach
- **Key components  (Web, Semantic, Search, Document, API)**
- **Functional Goals**
	- Semantic connection
	- Machine access
	- Cross site referencing

> *Notice: for this talk I will try to move quickly to the functional goals section*
---
# Architecture

```md
# Docker based
All elemented deploy from Docker files (most included 
at github)
Use official containers for things like Mongo and others
we can

# Golang
Development done in a modern web centric language.  

# In the Open; Github, Trello, Slack

# Polyglot Persistence  (all containerized)
- Triplestore (Blazegraph) for graphs
- MongoDB Mostly for core images & other blobs (some spatial)
- Relational (Janus) (and perhaps CSDCO and CHRONOS)
```
---

# Key components
Web

```html
Linked Open Data

HTML5 approaches including web components

Responsive design for mobile access 

Leaflet (and leaflet components) for maps

Polymer and other components for UI elements
```

---

# Key components


Semantic
```html

```
---

# Key components


Search (free text)
```html
Based on Bleve 

Allows mutli-index and faceted results.

Low level, so easy to integrate in but requires extra 
effort in the UI area.  

```
---

# Key components


Documents and API
```html
Documents stored in MongoDB (GridFS)
Potential for mutli-server approach for speed and
redundancy

API in Go with Swagger definitions
The APIs are still a quickly developing apsect.  Looking
to use a stable, dev, beta breakdown for them and note this
in the Swagger

```
---

## Functional Goals


|Function|Description|
|:-:|:-|
|**Semantics**|default|`<!-- $theme: default -->`
|**Machine Access**|gaia|`<!-- $theme: gaia -->`
|**Cross site referencing**|gaia|`<!-- $theme: gaia -->`


---


## Thanks! :+1:

### https://github.com/yhatt/marp

Copyright &copy; 2016 [Yuki Hattori](https://github.com/yhatt)
This software released under the [MIT License](https://github.com/yhatt/marp/blob/master/LICENSE).