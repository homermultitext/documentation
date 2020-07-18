---
layout: page
title:  Indexing non-textual features
parent: Guide for editors
nav_order: 2
---



## Overview

- We record non-textual features in delimited-text tables
- We keep these tables in the `collections-data` directory of your editing repository


### Scholion markers

We record the placement of markers in the *Iliad* text that link scholia to the text.  In the Venetus B and Upsilon 1.1, these are usually numbers;  in the Burney 86, they are regularly marked with dingbats.

Here is an example of a numeric marker from folio 225 verso of the Upsilon 1.1.

![](http://www.homermultitext.org/iipsrv?OBJ=IIP,1.0&FIF=/project/homer/pyramidal/deepzoom/hmt/e3bifolio/v1/E3_225v_226r.tif&RGN=0.3532,0.1847,0.01439,0.02257&wID=200&CVT=JPEG)

We record scholion markers in the `collections-data` directory of your editing repository.

We need five pieces of information.

1.  A URN identifying the marker. These only need to be unique, so if you're editing all the hyphens on a given page, for example, it's enough to create identifiers in a form like PAGE_COUNT with a running count for each. (The example below records the first marker on page 225 verso of the Upsilon 1.1. as  `urn:cite2:hmt:e3markers.v1:225v_1`.)
2. A "reading" of the marker.  For numeric markers, treat this as though you were editing the text in a document.  The example below records the marker as `<num>α</num>`.  If the marker is a dingbat, enter the URN for the dingbat instead. (You can use this [table of dingbats](https://github.com/homermultitext/hmt-authlists/blob/master/dingbatviewer.md) to find the right URN.)
3. A URN for a region of an image illustrating the marker.
4. The URN for the scholion this marker connects to.
5.  A URN for the text that the marker is attached to. Use `@1 extended notation to provide the text contents that the hyphen unifies.



```
#!ctsdata
urn#reading#image#scholion#text
urn:cite2:hmt:e3markers.v1:225v_1#<num>α</num>#urn:cite2:hmt:e3bifolio.v1:E3_225v_226r@0.3532,0.1847,0.01439,0.02257#urn:cts:greekLit:tlg5026.e3.hmt:17.E3_225v_1#urn:cts:greekLit:tlg0012.tlg001.e3:17.56@ἄνθει+λευκῷ
```





### Hyphens ("slurs")

Hyphens are marks that look like musical slurs.  Here's an example on the word Παναχαιῶν in *Iliad* 10.1 to prevent you from interpreting it as two separate words:

![](http://www.homermultitext.org/iipsrv?OBJ=IIP,1.0&FIF=/project/homer/pyramidal/deepzoom/hmt/vaimg/2017a/VA126RN_0298.tif&RGN=0.4825,0.2141,0.1131,0.0173&wID=5000&CVT=JPEG)


We record hyphens in the `collections-data` directory of your editing repository.

We need three pieces of information:

1. a URN identifying the hyphen.  These only need to be unique, so if you're editing all the hyphens in a given book, for example, it's enough to create identifiers in a form like `BOOK_COUNT` with a running count for each.  (The example below records the first hyphen in book 10 of the Venetus A as `urn:cite2:hmt:venAslur.v1:10_1`.)
2. a URN identifying the text where the hyphen occurs.  Use `@` extended notation to provide the text contents that the hyphen unifies. Here, the passage is `urn:cts:greekLit:tlg0012.tlg001.msA:10.1@Παναχαιῶν`
3. a URN for a region of an image illustrating the hyphen


The data file has two header lines, followed by rows of `#`-delimited data.  Here's the beginning of a file for book 10 of the Venetus A.

```
#!ctsdata
urn#text#imageroi
urn:cite2:hmt:venAslur.v1:10_1#urn:cts:greekLit:tlg0012.tlg001.msA:10.1@Παναχαιῶν#urn:cite:hmt:vaimg.2017a:VA126RN_0298@0.4825,0.2141,0.1131,0.0173
```

#### URNs for collections for hyphens

- Venetus B: `urn:cite2:hmt:vbslurs.v1:`
- Upsilon 1.1: `urn:cite2:hmt:e3slurs.v1:`
- Burney 86: `urn:cite2:hmt:burney86slurs.v1:`




#### URNs for collections of markers

- Venetus B: `urn:cite2:hmt:vbmarkers.v1:`
- Upsilon 1.1: `urn:cite2:hmt:e3markers.v1:`
- Burney 86: `urn:cite2:hmt:burney86markers.v1:`
