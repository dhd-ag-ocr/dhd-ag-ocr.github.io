# OCR-Arbeitstreffen

### ORT

ULB Halle, August-Bebel-Straße 13, Raum 311

### Twitter

\#ocrHalle

### Vorstellungsrunde    10–12 Uhr

1. Einführung 
2. Nasarek @RNasarek GitHub: rnsrk
3. Brenn @galdring Github: galdring
4. Büttner (nashi) Github: @andbue
5. Landes
6. Baierer (OCR-D)
7. Reul Github: @chreul
8. Christlein/Weichselbaumer
9. Dahnke

### Mittagspause         12–13 Uhr

### Werkstattgespräch    13–17 Uhr

#### Themenbereiche für das Werkstattgespräch am Nachmittag:

- **Technische Fragen:** Evaluation, GroundTruth Bottleneck, Handschriftenerkenung, Seitensegmentierung, Best Practices für OCR-Training, GT-Repos und -Formate

##### Ground Truth
###### DTA: Alignment von DTABf/TEI und OCR (=>GroundTruth Bottleneck)
   Vorteile: Detaillierte GT, inkl. Schriftwechsel, Formatierung, Druckfehler, Regionenklassen etc. pp. 
   Vorarbeiten:
 Johannes Baiter Github@jbaiter, [ArchiScribe](https://github.com/jbaiter/archiscribe)
 goethefind.cis.uni-muenchen

###### Daten teilen: 
Teilen von PageXML (mit Koordinaten und Text) um Lizensierungen zu umgehen (+ IIIF-Manifest)

###### Entwicklung:
GitHub Repos für:
DTA-Scraper
ScanTailor-Methoden exponieren
    - Methoden ausfindig machen
    - Methoden in *Python* exposieren

###### Spezialzeichen:

Spezialzeichen für [Teuthonista](https://de.wikipedia.org/wiki/Teuthonista_(Lautschrift)) [als](https://www.unicode.org/L2/L2012/12269-n4296-latin-chi.pdf) [Unicode](http://www.pentzlin.com/TeuthonistaUnicode1.pdf) (zu viele Zeichen für virtuelle Tastatur):
Eingabemethode im Betriebssystem installieren (wie IPA-Lautschrift, muß aber womöglich selbst definiert werden, z.B. mit `xkeycaps`)

###### Binarisierung

OLENA: https://www.lrde.epita.fr/wiki/Olena

https://github.com/OCR-D/ocrd_olena

https://github.com/glazzara/olena/tree/master/scribo/src/binarization

###### Preprocessing mit Scantailor
ScanTailor enhanced löst das Koordinatenproblem
- keine API (Methoden (in OpenCV) exponieren (portieren C++ nach Python))

###### Layouterkennung

Problem fließende Fußnoten: am besten mit der Hand 

###### Institutionalisieren

Dhd-Arbeitskreis anmelden(?) + lokaler Arbeitskreis
GitHub Repro mit Bearbeitungsrechten

https://github.com/UB-Mannheim/ocr-fileformat

###### Handschriften
neuere neuronalen Netze kommen damit klar (Calamari backend?)
Problem Zeilensegmentierung ()
[Computer Vision Lab | TU Wien](https://github.com/tuwien)
[verfügbare Methoden: Demoseite der DIVA-Group, Fribourg](http://wuersch.pillo-srv.ch/#/algorithms)
[sehr genaue, aber sehr langsame (5h pro Seite) Methode, nicht auf Github, aber bei Bedarf von Mathias Seuret (FAU) mathias@seuret.com zu bekommen.] (https://ieeexplore.ieee.org/abstract/document/8270154)
    
###### Best-Practise für OCR-Training
Uwe Springman: Robbentechnik, Stückweise mehr Trainingsdaten (Wie feingranular darf das Modell sein: viele Modelle für einzelne Dokumente bis  ein Modell für alle Dokumente)
Modell-Robustheit über Varianz oder Einheitlichkeit der Zeichen

Knowledge-Base von OCR4All:

Was sind die Use-Cases?
Keine selektive Auswahl, lohnt sich nicht vom Aufwand. 
Active Learning (Welche Zeilen wurden nicht gut erkannt? Vervielfachen!)

Warum gibt unterschiedliche Software auf dem selben Material eine unterschieldich Performance? (Tesseract vs. Calamari)

Evaluationsszenarien deutlich formulieren

Papers zu BP:
Für Calamari bzw. jede Software für sich

Auswirkung der Auflösung:
\+ 300 auf 500 bringt was vs. 
\- 300 auf 600 bringt nichts (hängt vom Ausgangsmaterial ab)

Threshold
\+ höherer Threshold

Erkenntnisse + Daten nach und nach sammeln: GitHub-Repo? Bei OCR-D publizieren

Deep Learning Hackathon Dresden 2019 https://indico.mpi-cbg.de/e/d3hack2019-cfa

Graustufe oder Binarisiert? 

- **Benutzbarkeit:** Formate vereinheitlichen, Konvertierung verbessern, Einstiegshürden reduzieren, Praxistauglichkeit erhöhen

- **Vermittlung:** Über Fortschritte und Möglichkeiten informieren, Zugang erleichtern, Arbeitsabläufe vereinheitlichen

###### Benutzer heranführen
Einheitliche Umgebung beim Workshop ist wichtig (VM ist da die einfachste und schnellste Lösung)
VM mit aller Software bereitstellen (alles drin, aber groß und schwer zu handhaben, darob schwieriger Datenaustausch)
Docker unter Windows schlecht performed schlecht

Windows 10 Linux Subsystem aktivieren 
Besser: Leute dahin bringen Console zu benutzen und OCR4All/Nashi als Oberfläche
Vagrant-File für virtuelle Maschine 

- **Institutionalisierung** Wie miteinander kommunizieren

## Fazit: To Do
Protokoll säubern @ Robert Nasarek
VM erstellen @ Florian Landes
Dhd-Arbeitskreis anmelden @ Michael Dahnke
DTA-Scraper/PageXML Alignierung
ScanTailor OpenCV Methoden (Alignierung, Deskewing, Despeckling, Cropping) in Python implementieren
Best-Practice Wiki @ Michael Dahnke + Konstantin Baierer + Daniel Brenn
Termin Videokonferenz ab 21.07.2019 @ Michael Dahnke 
Fraktur Modell bei ocropy-wiki eintragen @ RN

### Abschlussrunde: Evaluation und Zusammenfassung 17–18 Uhr

### Gemeinsames Abendessen & Ausklang ab 18:30 Uhr

### Kontaktadressen:

michael.dahnke@gmx.de (+49-176-48156690)
robert.nasarek@geschichte.uni-halle.de (0176 434 22 77 4)
florian.landes@gmx.de
daniel.brenn@bibliothek.uni-halle.de


## Notes

* Nasarek Intro
  * Binarisierung: Wozu eigentlich?
  * einheitlicher zeichensatz: Unicode mit NFC normalisierung; Mappen, Junicode, MUFI-Initative und Fonts; 
  * GT guidelines: ocr-d.github.io/gt

* Daniel Brenn

  * ABBYY fuer historische Drucke wird kaum bis gar nicht weiterentwickelt
  * Frage Dahnke: Wie Layout-Erkennung und Verknüpfung von Artikeln/Anzeigen, insbesondere über mehrere Seiten?
  * Frage Dahnke: Normalisierung? Was heißt Massendigitalisierung? Was soll Endprodukt sein? Ausgezeichnet? Unausgezeichnet?
  * ScanTailor für Preprocessing: Gut automatisierbar? (kmw: nein!)
  * Parallelisierung von Tesseract: Overhead für Threading, Performance ohne Parallelisierung in tesseract selbst?
  * Kitodo / zedOCR Setup
  * Arabisches OCR => kraken / openisil

* Andreas Büttner

  * JS-compilierte OCR-Engines im Browser?
  * Ground Truth teilen?
  * Transkriptionsrichtlinien? Insb. auflösen von Scribal Abbreviations etc.
  * Segmentierung als Teil des Werkzeugs notwendig? Import von (vorsegmentiertem) PAGE-XML_

* Florian Landes

  * Border Removal nicht mit ScanTailor moeglich weil Koordinaten sich verschieben (kmw: aber [`scantailor` enhanced](https://github.com/scantailor/scantailor/tree/enhanced)!)
  * Workflow in bash mit ImageMagick für Vorverarbeitung
  * Mapping der Koordinaten von Absätzen anhand der Zeichenzahl aus der Edition. clevere heuristik bei einheitlicher Schriftgroesse.
  * Transkription mit Aletheia? 

* Konstantin Baierer (OCR-D) 

     * Texterkennung auf Digitalisaten VD16–VD18; Vorgaben? Normalisierung? (kmw: Vgl. GT-Richtlinien!)
     * Modellsammlung? Sollen diese Modelle frei bleiben und frei verfügbar sein? (kmw: Unbedingt!)
     * Weiterentwicklung »Tesseract«? (kmw: Ja!)
     * GT-Repo: Copyright-Probleme?

* Christian Reul
    * Kann ich mit OCR4all binarisieren? (chreul: ja: »ocropus-nlbin«.)
    * Transkriptions-UI: WYSIWYG weniger ergonomisch als »ocropus-gtedit«

* Nikolaus Weichselbaumer

    * Alternative zur Schriftartenerkennung: Ocropy trainieren auf Alphabet das Schriftarten repraesentiert. Ausprobiert? Vergleich mit der RNN-Methode?
