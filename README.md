# CSAF-Template des CERTVDE

## Lizenz

CERT@VDE CSAF Template © 2024 by CERT@VDE is licensed under CC BY-NC 4.0. To view a copy of this license, visit https://creativecommons.org/licenses/by-nc/4.0/

## Über das Repository

In diesem Repository stellt das CERTVDE das Template CSAF-Dokument bereit, dass den minimalen
und/oder üblichen Inhalt eines CSAF-Advisorys beim CERTVDE beinhaltet.

## Wording / Glossar

Es werden die Begriffe nach [rfc2119](https://datatracker.ietf.org/doc/html/rfc2119) verwendet, insbesondere:
- **MUST**: Dieser Abschnitt muss ausgefüllt oder bearbeitet werden
- **SHOULD**: Dieser Abschnitt sollte ausgefüllt/bearbeitet werden. Wird er ausgelassen muss dies begründbar sein.
- **MAY**: Der Abschnitt ist Optional.

## Template

Das aktuellste Template befindet sich [hier im Repository](TEMPLATE-vde-1900-0815.json)
Bei Anmerkungen oder Änderungsbedarf dürfen gerne auch die Issues verwendet werden.

## Dokumentation

Die Dokumentation befindet sich im hier im Projekt-Wiki (Link ToDo)

## Nummernkreise für CSAFPIDs

Bitte wenn möglich die Nummernkreise für CSAFPIDs beachten:

## CSAFPID-Bereiche ( Vorschläge)

Die hier gemachten Vorschläge für die IDs dienen dazu, die Bearbeitung und Überprüfung eines CSAF-Dokumentes zu vereinfachen. Sie sind keine zwingende Vorgabe für CSAF, das nicht einhalten dieser Empfehlung kann allerdings für Verzögerungen in der Freigabe führen.

### Übersicht

| Kategorie | Status | Nummernkreis |
|:------ |:------:| ------:|
| Hardware | affected | CSAFPID-11xxx |
| Hardware | fixed | CSAFPID-12xxx |
| Firmware | affected | CSAFPID-21xxx |
| Firmware | fixed | CSAFPID-22xxx |
| Relationen | affected | CSAFPID-31xxx |
| Relationen | fixed | CSAFPID-32xxx |
| Software | affected | CSAFPID-51xxx |
| Software | fixed | CSAFPID-52xxx |
| OS | n/a | CSAFPID-90xxx |


### Hardware 1xxxx

#### Affected 11xxx

**Betroffene Geräte** (Hardwarerevisionen) sollten in dem ID-Bereich **CSAFPID-11xxx** (also -11000 bis -11999) liegen

#### Fixed 12xxx

**Gefixte Geräte** (Hardwarerevisionen) sollten in dem ID-Bereich **CSAFPID-12xxx** (also -12000 bis -12999) liegen.  
**Achtung!** _Dieser Bereich ist in der Regel unbenutzt, es gibt selten Fälle in dem er bei uns genutzt wird. Die Verwendung bedeutet in der Regel einen Hardwareaustausch._

### Firmware 2xxxx

#### Affected 21xxx

Bereich für **betroffene Firmwareversionen** **CSAFPID-21000** bis **-21999**. 
Hier werden typischerweise Versionsbereiche (<, <=) verwendet.

#### Fixed 22xxx

Bereich für **bereinigte Firmwareversionen** **CSAFPID-22xxx** (**-22000** bis **-22999**). 
Hier wird die gefixte Firmwareversion angegeben. Typischerweise genau eine Version, da es keine Garantie gibt, dass die Schwachstelle in zukünftigen Versionen nicht wieder eingebaut wird (auch wenn wir nicht hoffen, dass das nochmal passiert).

### Relationen 3xxxx

Hier werden die Zuordnungen zwischen Hardware und Firmware hergestellt. Also FirmwarePID installed on HardwarePID...

#### Affected 31xxxx

**Betroffene Relationen** erhalten eine ID aus dem Bereich **CSAFPID-31xxx**.

#### Fixed 32xxx

**Bereinigte Relationen** erhalten eine ID aus dem Bereich **CSAFPID-32xxx**.

### Software 5xxxx

Im Softwarebereich müssen wir für gewöhnlich mit weniger Relationen arbeiten, das erspart einige Secvisogram-Klicks.

#### Affected 51xxx

**Betroffene Software** ist in dem Bereich **CSAFPID-51xxx** gut aufgehoben.

#### Fixed 52xxx

Software die von der **Schwachstelle befreit** wurde sollte in dem Bereich **CSAFPID-52xxx** liegen.

### Betriebssysteme 90xxx

Betriebsysteme oder Versionen externer Software (zum Beispiel Java) die in einer Relation "installed on" als Ziel verwendet können.



---
(english version)
## CSAFPID ranges (suggestions)

The suggestions made here for the IDs serve to simplify the processing and checking of a CSAF document. They are not a mandatory requirement for CSAF, but failure to comply with this recommendation can lead to delays in release.

### Overview

| Category | Status | Number range |
|:------ |:------:| ------:|
| Hardware | affected | CSAFPID-11xxx |
| Hardware | fixed | CSAFPID-12xxx |
| Firmware | affected | CSAFPID-21xxx |
| Firmware | fixed | CSAFPID-22xxx |
| relations | affected | CSAFPID-31xxx |
| relations | fixed | CSAFPID-32xxx |
| Software | affected | CSAFPID-51xxx |
| Software | fixed | CSAFPID-52xxx |
| OS | n/a | CSAFPID-90xxx |


### Hardware 1xxxx

#### Affected 11xxx

**Affected devices** (hardware revisions) should be in the ID range **CSAFPID-11xxx** (i.e. -11000 to -11999)

#### Fixed 12xxx

**Fixed devices** (hardware revisions) should be in the ID range **CSAFPID-12xxx** (i.e. -12000 to -12999).  
**This range is usually unused, there are rare cases in which it is used by us. Using it usually means replacing the hardware.

### Firmware 2xxxx

#### Affected 21xxx

Range for **affected firmware versions** **CSAFPID-21000** to **-21999**. 
Version ranges (<, <=) are typically used here.

#### Fixed 22xxx

Range for **fixed firmware versions** **CSAFPID-22xxx** (**-22000** to **-22999**). 
The fixed firmware version is specified here. Typically exactly one version, as there is no guarantee that the vulnerability will not be reintroduced in future versions (although we do not hope that this will happen again).

### Relations 3xxxx

The assignments between hardware and firmware are created here. So FirmwarePID installed on HardwarePID...

#### Affected 31xxxx

**Affected relations** receive an ID from the range **CSAFPID-31xxx**.

#### Fixed 32xxx

**Fixed relations** receive an ID from the range **CSAFPID-32xxx**.

### Software 5xxxx

In the software area, we usually have to work with fewer relations, which saves a few Secvisogram clicks.

#### Affected 51xxx

**Affected software** is in good hands in the **CSAFPID-51xxx** area.

#### Fixed 52xxx

Software that has been released from the **vulnerability** should be in the **CSAFPID-52xxx** range.

### Operating systems 90xxx

Operating systems or versions of external software (e.g. Java) that can be used as a target in an “installed on” relation.

