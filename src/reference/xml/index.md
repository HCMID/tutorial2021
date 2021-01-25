---
title: "XML usage"
layout: page
nav_order: 4
parent:  "Reference"
grand_parent:  "HC MID tutorial"
---



# Concise summary of typical XML usage

While every project edits distinct kinds of texts, the following usage of TEI-compliant XML is typical for MID projects, and can be converted to diplomatic and normalized editions using a `MidDiplomaticBuilder` and `MidNormalizedBuilder`.

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


