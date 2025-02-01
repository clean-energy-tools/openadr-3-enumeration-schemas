
A proposed feature for OpenADR 3.1 is adding JSON Schema files that concretely describe the Enumeration tables in the OpenADR 3 Definitions document.

The enumeration tables describe part of the vocabulary of communication between OpenADR 3.x VENs and VTNs.

The JSON Schema files are meant to be a concrete specification that can be used by OpenADR implementors to auto-generate data validation code.

This repository contains three documents describing aspects of adopting use of these schema files.  The documents are described in the table below, and they are available to read online and as PDF.

The initial goal is for the Reference Implementation to use the schemas, and for the Compliance Test suite to validate that a VTN or VEN correctly recognizes correct and incorrect enumerated values.

My (David Herron) current task towards adoption of these schemas is giving advice as to how the OpenADR Reference Implementation (RI) and test suite should change, and specifically what kind of testing is required.

Online         | PDF | Description
---------------|-----|------------------
[Recommended Implementation for utilizing enumeration schemas in the OpenADR RI](./documents/RI-Implementation.md) | [PDF](./PDF/RI-Implementation.pdf) | Discusses how a VEN or VTN should implement data validation of OpenADR 3 objects, and specifically validating the values covered by the enumeration tables
[RI testing that enumerated values are correct](./documents/RI-Testing-Enumerated-Values.md) | [PDF](./PDF/RI-Testing-Enumerated-Values.pdf) | Discusses how, after implementing data validation in the RI, the test suite should be extended for to ensure that an OpenADR implementation correctly validates correct and incorrect enumerated values
[Considering extensions to enumeration tables using Schema files](./documents/Extensions-Enumerations.md) | [PDF](./PDF/Extensions-Enumerations.pdf) | Discusses how the existence of JSON Schemas for the enumeration tables opens the door to private extensions to those tables, and concretely communicating such extensions among partner organizations.

## Call for Collaboration

It is meant that the OpenADR team collaborate on the content of these documents and guidance on adopting the schemas.

Raise issues - submit ideas via pull request - etc

## Building the PDFs

The documents are written with straight Markdown and should display correctly on GitHub.

The PDFs are built using [`@akashacms/pdf-document-builder`](https://akashacms.github.io/pdf-document-construction-set/guide/index.html).

To setup the build tools, you must have Node.js 20.x or later installed, then run:

```shell
$ npm install
```

To rebuild the documents run:

```shell
$ npm run build:all
```

To edit one of the files and have live rebuild:

```shell
$ npm run watch:impl
$ npm run watch:testing
$ npm run watch:extend
```

To have a live preview in a web browser which auto-updates as you edit:

```shell
$ npm run preview
```