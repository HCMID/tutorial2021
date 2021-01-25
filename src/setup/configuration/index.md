---
title: "Configuring texts for editing"
layout: page
nav_order: 2
parent:  "Setting up a repository"
grand_parent:  "HC MID handbook"
---




# Configuring texts for editing


The file `config/catalog.cex` is a delimited-text file with an entry for each text you are editing.  

You can look up appropriate values to enter for your text using the tables in the [reference section](../../reference/) of this tutorial.

Its columns are:

1. the text identified by CTS URN
2. labels for each tier of the citation scheme, separated by commas. E.g., `book,line` would be an appropriate entry to cite a text like the *Iliad* by book and line.  
3. name of the text group (e.g., "Homeric poetry")
4. title of the work (e.g., "*Iliad*")
5. label for the version (e.g., "MID edition")
6. optional label for  a specific exemplar of that version:  for manuscript material, this will normally be empty.  
7. the value `true` if the edition is available, or `false` if the text is cataloged but no edition is available.  
8. the three-letter code for the language of the text in ISO 639 (e.g., `grc` for ancient Greek).

Example entry:

```
urn|citationScheme|groupName|workTitle|versionLabel|exemplarLabel|online|language
urn:cts:latinLit:phi0881.phi003.bern88:|line|Germanicus|Aratea|HC edition||true|lat
```

The file `config/citation.cex` is a delimited-text file with an entry corresponding to each entry for an online text in the `catalog.cex` file.  Its columns are:

1. the text identified by CTS URN.  This should match an entry in the `catalog.cex` file.
2. the name of the corresponding file in the `editions` directory.
3. the name of a Julia function that converts the file to the OHCO2 model.
4. julia code to instantiate a `CitableTextBuilder` for building diplomatic editions
5. julia code to instantiate a `CitableTextBuilder` for building normalized editions
6. julia code to instantiate an `OrthographicSystem` for validating and tokenizing editions.


Example entry:

```
urn|file|converter|diplomatic|normalized|orthography
urn:cts:latinLit:phi0881.phi003.bern88:|aratea.xml|poeticLineReader|LiteralTextBuilder("Literal text builder","rawtext")|LiteralTextBuilder("Literal text builder","rawtext")|SimpleAscii()
```
