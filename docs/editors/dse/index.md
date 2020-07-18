---
layout: page
title:  Indexing DSE records
parent: Guide for editors
nav_order: 1
---



## Conceptual model

Our editing work starts from a specific model of a digital scholarly edition (DSE):  every citable passage of text occurs on a citable physical surface (such as a page of a manuscript), and is illustrated by a citable image.

We can express that idea with three URNs:  a CTS URN identifying the text passage, a CITE2 URN for the page, and a CITE2 URN for an image (usually, a region of interest on a larger image).


## Recording DSE relations

We record these triples in delimited-text files.  Each row represents one passage of text. Columns, separated by the `#` character, record the text passage, an image URN copied from the [Homer Multitext project Image Citation Tool](http://www.homermultitext.org/ict2/), and a URN for the page.

Here's an example of what a single DSE record looks like:

```
passage#imageroi#surface
urn:cts:greekLit:tlg0012.tlg001.e3:23.1#urn:cite2:hmt:e3bifolio.v1:E3_293v_294r@0.4863,0.4409,0.2771,0.05960#urn:cite2:hmt:e3.v1:294r
```
## Validating and verifying

Validation reports list how many DSE records were composed of syntactically correct citations to valid data in your repository.  If we have only the single line given above in our DSE index and no corresponding text passage, the error report looks like this:

---

![failed dse](https://neelsmith.github.io/transmission-evolution/imgs/dse-failed-validation.png)
