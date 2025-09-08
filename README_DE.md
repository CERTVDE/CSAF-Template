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

## Revisionen / Versionen des CSAF Dokuments

Wir verwenden Semver als Versionsschema für die CSAF Dokumente. Dabei gibt es folgende Richtlinien:
Das Schema besteht aus Major.Minor.Patch, also zum BEispiel 2.3.1 Wobei hier 2 die Major-, 3 die Minor- und 1 die Patchversion darstellt.
Wird **Minor** erhöht, so wird **Patch** auf 0 gesetzt.
Wird **Major** erhöht, so werden **Minor und Patch** jeweils auf 0 gesetzt.


Die erste Veröffentlichung hat Version 1.0.0

**Patch** wird erhöht bei kleineren Änderungen am Dokument, die technisch nicht relevant sind. Das können Typos und Layoutfehler sein, oder aber auch Änderungen in den Metadaten oder CSAF internen Daten, wie zum Beispiel Korrekturen eines Revisionstextes.

**Minor** wird erhöht bei kleinen Änderungen die aber technisch relevant sind. Wie zum Beispiel das hinzufügen einzelner Produkte oder andere Änderungen mit keinem allzu großen Impact.

**Major** wird erhöht bei großen technisch relevanten Änderungen wie zum Beispiel:
 - hinzufügen oder entfernen ganzer Produktfamilien
 - Änderungen/Updates an CVE Einträgen
 - andere große Änderungen die eine Neubewertung des Advisorys nötig gemacht haben


## Variablen, Referenzen, Tags und Kommentare

Das Template verwendet einige Definitionen um die spätere Bearbeitung oder Verarbeitung zu vereinfachen.

### Variablen

Werden für gewöhnlich mit ihrem außerhalb dieses Dokuments definierten Wert ersetzt. Sollte kein
Wert gesetzt sein, wird der Standardwert (hinter dem "=") verwendet oder kein Inhalt eingesetzt.
Die Verarbeitung und das Einsetzen entsprechender Werte muss dann außerhalb des Templates mit 
entsprechenden Tools und Scripten erfolgen.

`${Variable01}$`  
definiert eine Variable namens _Variable01_. Diese muss außerhalb des Dokuments definiert
werden oder bleibt leer. 

`${Variable02=Beispielwert hier}$`  
definiert eine Variable namens _Variable02_ diese hat den Standardwert: _Beispielwert hier_,
wenn sie nicht anderweitig einen Wert zugewiesen bekommt.

`${Variable03=Ein anderer Standardwert, der "${Variable02}$" von Variable02 beinhaltet}$`  
definiert eine Variable namens _Variable03_ die den Wert:
_Ein anderer Standardwert, der "Beispielwert hier" von Variable02 beinhaltet_, 
wenn Variable02 und Variable03 nicht anders gesetzt werden.  


### Referenzen

...sind Links zu Werten, Objekten oder Arrays in dem Template ansich. Zur verlinkung
wird [JSONPath](https://datatracker.ietf.org/doc/html/rfc9535) verwendet

`%{$.document.tracking.id}%`  
verwendet den referenzierten Wert des document tracking Objektes: `[TODO][MUST]VDE-1900-0815` 

`${$.document.notes[0]}$`  
verweist auf das komplette Objekt der ersten Document Note : `"audience": "csaf creator", "category": "other", "text": "[CERT@VDE CSAF Template](https://github.com/CERTVDE/CSAF-Template) © 2024 by [CERT@VDE](https://certvde.com) is licensed under [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/?ref=chooser-v1) \n\nThis document note may only be removed in order to create a CSAF advisory based on this template.", "title": "LICENSE"`  

`${$.document.notes[0].title}$`  
verweist auf den Wert von title im ersten Document Note Objekt: `"LICENSE"`

### Tags

Tags sind Markierungen oder Hinweise zu Aufgaben, die noch zu erledigen sind.
Das Tag `[TODO]` markiert Stellen im Template die zwingend bearbeitet werden müssen. Die Inhalte
dort enthalten eventuell noch Beispieldaten, die entfernt werden müssen, oder hier sind einfach 
noch Pflichtangaben zu machen. 
An zweiter Stelle kann ein Tag mit einem Begriff aus RFC2119 verwendet werden, also  
`[MUST]`, `[SHOULD]` oder `[MAY]`.
An dritter Stelle kann optional der Tag `[REMOVE]` stehen. Das ist ein Hinweis, dass der Abschnitt
oder das Objekt vollständig entfernt werden kann.

### Kommentare

Kommentare werden im Template als Hinweise für den Anwender genutzt. Sie können mit Tags 
beginnen. Dabei ist die Reihenfolge (siehe Tags) einzuhalten. Vor dem Veröffentlichen
eines CSAF müssen alle Kommentare aus dem Dokument entfernt werden.

`#{Hier ist ein Kommentar}#`  
Der Kommentar "_Hier ist ein Kommentar_".

`#{[TODO][SHOULD] Ein Kommentar kann auch Werte von Variablen beinhalten "${Variable02}$"}`  
Der Kommentar: '_[TODO][SHOULD] Ein Kommentar kann auch Werte von Variablen beinhalten "Beispielwert hier"_'

`#{Ein Kommentar kann auch auf eine Referenz verweisen, wie hier: "%{$.document.tracking.id}%"}`  
Auch Referenzen können verwendet werden: '_Ein Kommentar kann auch auf eine Referenz verweisen, wie hier: "[TODO][MUST]VDE-1900-0815"_'


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

