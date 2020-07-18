---
layout: page
title:  Editing XML
parent: Guide for editors
nav_order: 3
---



### Summary of character set usage

- alphabetic characters: alphabetic α-ω in upper or lower case. They may be combined with accents and/or breathings in the Unicode Greek range.  
- punctuation:
    -   period = `.`
    -   comma = `,`
    -   interrogation mark = `;`
    -   high stop = `~`
    -  the "second" or "doubled" grave accent (a punctuation mark occasionally included in Venetus B and Upsilon 1.1 to mark some kind of clausal or phrasal unit) = `⸌` (Unicode U+2e0c)
    -   "end-of-scholion/unit" marker:  `⁑` (Unicode U+2015)
- quantity:
    -   macron = `_` (underscore)
    -   breve = `^`
- "floating" characters:  our manuscripts sometimes create combinations of accents, breathings and other marks that we do not encounter in modern typeset Greek, and that cannot be encoded with Unicode characters.  In those cases where you may need to add an additional diacritic character, use the following encodings:
    - "floating" diaeresis =  `+`



### Concise summary of XML usage

Our XML markup falls in 4 tiers:

1. *transcription level* (or, editorial status): unclear, gaps, etc
2. *tokenization level*: words, abbreviations, superlinear addtions, deletions, corrections, scribal multiforms, character strings
3. *editorial disambiguation level*: named entities
4. *discourse disambiguation*: quotations and citable references

At each level, the following TEI elements are allowed:


**Transcription level**

- `unclear`
- `gap`

**Tokenization level**


- `w`
- `num`
- `abbr/expan` choice
- `del` deleted by scribe (e.g., underdots)
- `add` text added (eg, above line)
- `orig/reg` choice: alternate reading offered (multiform)
- `sic/corr` choice: scribal correction

**Editorial disambiguation level**

Named entities with `@n` attribute with URN value:

- `persName`
- `placeName`
- `rs` with `@type` attribute


**Discourse level**


- `q` alone:  
    - quotation, work not extant
    - quoted example of language. Test: you would not  translate this when reading the text, e.g. explaining the declension of a noun by using another common Greek word as an example
- `cit` containing `q` and `ref`: quotation of extant work
- `title` with either CTS URN (extant work) or CITE2URN
- `rs` with `type="waw"` quoted expression not parseable as  a Greek word, e.g. "the letter σ"
