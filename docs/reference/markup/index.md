---
title: "Configuring markup schemes"
layout: page
nav_order: 1
parent:  "Reference"
grand_parent:  "HC MID tutorial"
---


# Configuring markup schemes

In `config/citation.cex`, the `converter` column defines how to transform text in your markup scheme to the common model of a sequence of citable nodes.

Use these tables to find an appropriate value for `converter` for your text.

## One-tier citation schemes


If your citation scheme...

| cites by | using TEI | like | then use | 
| --- | --- | --- | --- |
| simple poetic line | `/TEI/text/body/l` | Germanicus, *Aratea* | `poeticLineReader`|
| simple prose block | `/TEI/text/body/ab` | Aristonicus, *On Signs* | `simpleAbReader`|

## Two-tier citation schemes

If your citation scheme...

| cites by | using TEI | like | then use | 
| --- | --- | --- | --- |
| book and poetic line | `/TEI/text/body/div/l` | *Iliad* | `divLineReader`|
| section and  prose block | `/TEI/text/body/div/ab` | the Xanthos obelisk (TL 44) | `divAbReader`|


## Three-tier citation schemes

If your citation scheme...

| cites by | using TEI | like | then use | 
| --- | --- | --- | --- |
| book, scholion and part | `/TEI/text/body/div/div/div` | *scholia* to the *Iliad* | `threeDivReader`|

