---
title: "Configuring edition builders"
layout: page
nav_order: 2
parent:  "Reference"
grand_parent:  "HC MID handbook"
---


# Building diplomatic and normalized editions

Your archival TEI text is *multivalent*: every TEI `choice` element offeres the possibility of two different readings.   In `config/citation.cex`, the columns for `diplomatic` and `normalized` define how to compose from your XML a *univocal* edition with a single reading. *Diplomatic* editions reflect exactly what you read in your source document. *Normalized* editions reflect some further intervention (abbreviations expanded, or errors corrected, for example).

Many MID projects will be able to encode their editions competely using the TEI XML [summarized here](../xml/).  Projects that stay within those guidelines can use these configuration values :

- diplomatic edition: `MidDiplomaticBuilder("Diplomatic edition builder","dipl")`
- normalized edition: `MidNormalizedBuilder("Normalized edition builder","normed")`


If your project includes additional or different markup, you will need to use builders for diplomatic and normalized editions that take account of that.