---
title: "Orthography"
layout: page
nav_order: 3
parent:  "Reference"
grand_parent:  "HC MID handbook"
---


# Orthography

**TBA**



In config/citation.cex, the `orthography` column defines how to validate character usage and parse your text into a sequence of classified tokens.

Use these tables to find an appropriate value for converter for your text.

If your text...


| is in | and  | like | then use | 
| --- | --- | --- | --- |
| a Roman alphabet | uses only basic alphabetic, numeric and punctuation characters | original English translations of many documents | `simpleAscii()`
| Greek | uses standard literary orthography | the *Iliad*  |**TBA** |
| Greek | includes additional symbols from *scholia* |  *scholia* to the *Iliad* | **TBA** |
| Latin | distinguishes *u/v* and *i/j* | ? | **TBA** |
| Latin | distinguishes *u/v* but not *i/j* | ? | **TBA** |
| Latin | uses *u* and *i* for consonantal and vocalic values | HC edition of Hyginus, *Fabulae* | **TBA** |
| Lycian | uses ASCII-based encoding | HC edition of *Tituli Lycii* | `lycianAscii()` |
