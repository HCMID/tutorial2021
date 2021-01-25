---
title: "File organization"
layout: page
nav_order: 1
parent:  "Setting up a repository"
grand_parent:  "HC MID handbook"
---



# File organization

You can use the repository at  <https://github.com/HCMID/validatormodel> as a model.

1. Create a new github repository.
2. Add the following four directories to it:
   - `dse`.  Create at least one file with the extension `.cex`.  Add a header line by copying it from one of the model repository's `dse` files. 
   - `editions`.  Create an XML file for at least one text you fill edit.  As the editor, you will decide how to encode canonical citation for each of your texts.  Look at examples in the model repository so see how you can include this `xml-model` processing instruction, that will allow VS Code to validate your edition against the TEI schemas.
       `<?xml-model  href="https://vault.tei-c.org/P5/current/xml/tei/custom/schema/relaxng/tei_all.rng" schematypens="http://relaxng.org/ns/structure/1.0" type="application/xml"?>`
   - `notebooks`.   From the model repository, copy all the files in the `notebooks` directory into your directory.  Edit the file `MID.toml` to add appropriate values for the name and github repository of your project.
   - `config`.  Create a file named `catalog.cex` and a file named `citation.cex`.  Add a header line by copying it from the `catalog.cex` and `citation.cex` file of the model repository.  To validate your work, you will add an entry to the catalog and citation configuration files for each text that you edit.
