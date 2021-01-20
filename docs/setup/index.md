---
title: "Setting up a repository"
layout: page
nav_order: 2
parent:  "HC MID tutorial"
has_children:  true
---

# Setting up a repository

Your editing repository needs to

1. organize your work in directories following HC MID conventions.
2. add configuration entries for each text you edit.  


Normally, your team will do this set up once and never need to pay attention to it again once you start editing, but remember that if you start to work in the same repository on new texts, you'll need to add configuration entries for them.

You can also [refer to these instructions](./update/) if you need to update the copy of the validating notebook in your repository.

## 1. File organization

You can use the repository at  <https://github.com/HCMID/validatormodel> as a model.

1. Create a new github repository.
2. Add the following four directories to it:
   - `dse`.  Create at least one file with the extension `.cex`.  Add a header line by copying it from one of the model repository's `dse` files. 
   - `editions`.  Create an XML file for at least one text you fill edit.  As the editor, you will decide how to encode canonical citation for each of your texts.  Look at examples in the model repository so see how you can include this `xml-model` processing instruction, that will allow VS Code to validate your edition against the TEI schemas.
       `<?xml-model  href="https://vault.tei-c.org/P5/current/xml/tei/custom/schema/relaxng/tei_all.rng" schematypens="http://relaxng.org/ns/structure/1.0" type="application/xml"?>`
   - `notebooks`.   From the model repository, copy all the files in the `notebooks` directory into your directory.  Edit the file `MID.toml` to add appropriate values for the name and github repository of your project.
   - `config`.  Create a file named `catalog.cex` and a file named `citation.cex`.  Add a header line by copying it from the `catalog.cex` and `citation.cex` file of the model repository.  To validate your work, you will add an entry to the catalog and citation configuration files for each text that you edit.


## 2. Configuring texts for editing


The file `config/catalog.cex` is a delimited-text file with an entry for each text you are editing.  Its columns are:

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

## How do I update my validating notebook?

If your project's validating notebook is behind the current version available from [https://github.com/HCMID/validatormodel](https://github.com/HCMID/validatormodel), you should [follow these instructions](./update/) to update your notebook.