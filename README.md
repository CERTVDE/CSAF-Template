# CSAF Template of CERTVDE

## License

CERT@VDE CSAF Template © 2025 by CERT@VDE is licensed under CC BY-NC 4.0. To view a copy of this license, visit https://creativecommons.org/licenses/by-nc/4.0/

## About the repository

In this repository, CERTVDE provides the CSAF document template that contains the minimum
and/or usual content of a CSAF advisory published at CERTVDE.

## Wording / Glossary

The terms used are based on [rfc2119](https://datatracker.ietf.org/doc/html/rfc2119), in particular:
- **MUST**: This section must be completed or edited.
- **SHOULD**: This section should be completed/edited. If it is omitted, this must be justified.
- **MAY**: This section is optional.

## Template

The latest template can be found [in the repository](https://raw.githubusercontent.com/CERTVDE/CSAF-Template/refs/heads/main/TEMPLATE-vde-1900-0815.json).
If you have any comments or changes, please feel free to use the issues in the repository to discuss them.

## Revisions/versions of CSAF documents

We use Semver as the versioning scheme for CSAF documents. 
The following guidelines apply:
- The scheme consists of Major.Minor.Patch, for example 2.3.1, where 2 represents the major version, 3 the minor version, and 1 the patch version.
- If **Minor** is increased, **Patch** is set to 0
- If **Major** is increased, **Minor and Patch** are each set to 0
- The first released version is 1.0.0

**Patch** is increased for minor changes to the document that are not technically relevant. These can be typos and layout errors, or changes to metadata or CSAF internal data, such as corrections to a revision text.

**Minor** is increased for small changes that are technically relevant. These could be the addition of individual products or other changes that do not have a significant impact.

**Major** is increased for large, technically relevant changes, such as:
- Adding or removing entire product families
 - Changes/updates to CVE entries
 - Other major changes that have necessitated a reassessment of the advisory


## Variables, references, tags, and comments

The template uses a number of definitions to simplify subsequent editing or processing.

### Variables

These are usually replaced with their value defined outside this document. If no value is set, the default value (after the “=”) is used or no content is inserted.
The processing and insertion of corresponding values must then be done outside the template using appropriate tools and scripts.

`${Variable01}`

`${Variable01}$`  
defines a variable named _Variable01_. This must be defined outside the document
or it will remain empty. 

`${Variable02=Example value here}$`  
defines a variable named _Variable02_ which has the default value: _Example value here_,
if it has not been set a value elsewhere.

`${Variable03=Another default value that contains “${Variable02}$” from Variable02}$`  
defines a variable named _Variable03_ that has the value:
_Another default value that contains “Example value here” from Variable02_, 
if Variable02 and Variable03 are not set otherwise.  

### References

...are links to values, objects, or arrays in the template itself. To link,
 [JSONPath](https://datatracker.ietf.org/doc/html/rfc9535) is used

`%{$.document.tracking.id}%`  
uses the referenced value of the document tracking object: `[TODO][MUST]VDE-1900-0815` 

`${$.document.notes[0]}$`  
refers to the complete object of the first document note: `“audience”: “csaf creator”, “category”: “other”, ‘text’: "[CERT@VDE CSAF Template](https://github.com/CERTVDE/CSAF-Template) © 2024 by [CERT@VDE](https://certvde.com) is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/?ref=chooser-v1) \n\nThis document note may only be removed in order to create a CSAF advisory based on this template.", “title”: “LICENSE”`  

`${$.document.notes[0].title}$`  
refers to the value of title in the first Document Note object: `“LICENSE”`

### Tags

Tags are markers or notes for tasks that still need to be completed.
The tag `[TODO]` marks places in the template that must be edited. The content
may still contain sample data that needs to be removed, or there may simply be 
mandatory information that still needs to be entered. 
Secondly, a tag with a term from RFC2119 can be used, i.e.  
`[MUST]`, `[SHOULD]`, or `[MAY]`.
Thirdly, the tag `[REMOVE]` can be used optionally. This is a note that the section
or object can be removed completely.

### Comments

Comments are used in the template as notes for the user. They can begin with tags .
 The order (see Tags) must be observed. Before publishing
a CSAF, all comments must be removed from the document.

`#{Here is a comment}#`  
The comment “_Here is a comment_”.

`#{[TODO][SHOULD] A comment can also contain values from variables “${Variable02}$”}`  
The comment: '_[TODO][SHOULD] A comment can also contain values from variables “Example value here”_'

`#{A comment can also refer to a reference, as here: “%{$.document.tracking.id}%”}`  
References can also be used: '_A comment can also refer to a reference, as here: “[TODO][MUST]VDE-1900-0815”_'

## Number ranges for CSAFPIDs

Please note the number ranges for CSAFPIDs where possible:

## CSAFPID ranges ( Suggestions)

The suggestions made here for the IDs are intended to simplify the processing and verification of a CSAF document. They are not mandatory requirements for CSAF, but failure to comply with this recommendation may lead to delays in approval.

### Overview

| Category | Status | Number range |
|:------ |:------:| ------:|
| Hardware | affected | CSAFPID-11xxx |
| Hardware | fixed | CSAFPID-12xxx |
| Firmware | affected | CSAFPID-21xxx |
| Firmware | fixed | CSAFPID-22xxx |
| Relations | affected | CSAFPID-31xxx |
| Relations | fixed | CSAFPID-32xxx |
| Software | affected | CSAFPID-51xxx |
| Software | fixed | CSAFPID-52xxx |
| OS | n/a | CSAFPID-90xxx |


### Hardware 1xxxx

#### Affected 11xxx

**Affected devices** (hardware revisions) should be in the ID range **CSAFPID-11xxx** (i.e., -11000 to -11999).

#### Fixed 12xxx

**Fixed devices** (hardware revisions) should be in the ID range **CSAFPID-12xxx** (i.e., -12000 to -12999).  
**Attention!** _This range is generally unused; there are rare cases in which we use it. Its use usually means a hardware replacement.

### Firmware 2xxxx

#### Affected 21xxx

Range for **affected firmware versions** **CSAFPID-21000** to **-21999**. 
Version ranges (<, <=) are typically used here.

#### Fixed 22xxx

Range for **fixed firmware versions** **CSAFPID-22xxx** (**-22000** to **-22999**). 
The fixed firmware version is specified here. Typically exactly one version, as there is no guarantee that the vulnerability will not be reintroduced in future versions (even though we hope that this will not happen again).

### Relations 3xxxx

This is where the mappings between hardware and firmware are established. In other words, FirmwarePID installed on HardwarePID...

#### Affected 31xxxx

**Affected relations** are assigned an ID from the **CSAFPID-31xxx** range.

#### Fixed 32xxx

**Fixed relations** are assigned an ID from the **CSAFPID-32xxx** range.

### Software 5xxxx

In the software area, we usually have to work with fewer relations, which saves a few Secvisogram clicks.

#### Affected 51xxx

**Affected software** is well placed in the **CSAFPID-51xxx** range.

#### Fixed 52xxx

Software that has been **freed from the vulnerability** should be in the **CSAFPID-52xxx** range.

### Operating systems 90xxx

Operating systems or versions of external software (e.g., Java) that can be used as targets in an “installed on” relation.
