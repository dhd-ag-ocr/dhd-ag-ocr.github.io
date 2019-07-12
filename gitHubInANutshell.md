# Git in einer Nußschale

Für die lokale Bearbeitung von Dateien in einem GitHub-Repositorium oder das Speichern von Dateien in einem GitHub-Repositorium empfiehlt sich die lokale Bearbeitung der Dateien resp. des gesamten Repositoriums. Dafür ist die nachfolgende Anleitung geschrieben. Es wurde ein »MacBookAir7,2« mit »macOS High Sierra 10.13.6« benutzt.  

01. Herunterladen der Installationssoftware, eg. unter https://git-scm.com/downloads.
02. Alternatively, as it is said on this page:
	»If you already have Git installed, you can get the latest development version via Git itself:

	git clone https://github.com/git/git.«

[[https://git-scm.com/downloads](https://git-scm.com/downloads). Last access 21.06.2019]

03. Nach der Installation zu entsprechendem GitHub-Repositorium – in diesem Fall https://github.com/kba/ag-ocr – und die Pfadangabe wie auf gitHub_InANutshell01.png dargestellt kopieren.
04. Auf dem Rechner mit graphischer Benutzeroberfläche – Finder, Windows Explorer etc. – oder via Terminal (auch bekannt als BASH, Shell, cli; nachfolgend wird nur noch Ausdruck Terminal benutzt) an beliebiger Stelle ein Verzeichnis – vulgo Ordner – erstellen. Im konkreten Fall wird im Benutzerverzeichnis ein Unterverzeichnis »git« erstellt und dieses nachfolgend als ~/git bezeichnet: »mkdir git«
05. Mit Terminal in »~/git« gehen: »cd ~/git«
06. Repositorium in dieses Verzeichnis kopieren: »git clone https://github.com/kba/ak-ocr.git« und
07. »cd ak-ocr.git«.
6. Eine der wichtigen Eigenschaften von GitHub-Repositoria ist die Versionierung der Dateien, ie. es werden alle Änderungen an allen in einem GitHub-Repositorium bearbeiteten Dateien protokolliert und diese können gegebenenfalls rückgängig gemacht werden.
07. In jedem GitHub-Repositorium gibt es auf der obersten Ebene ein verstecktes Verzeichnis: ».git«. Analog kann auf der obersten Ebene eine ebenfalls versteckte Datei ».gitignore« angelegt werdne, in der Dinge notiert werden, die nicht versioniert werden sollen. Dazu gibt es auf zahlreichen Seiten vorgefertigte ».gitignore«-Dateien, die entsprechend angepaßt werden können.
08. Sind alle gewünschten Änderungen vorgenommen worden, ie. in Dateien geschrieben, neue Dateien angelegt, Dateien gelöscht etc., sind 

	10.1. die veränderten Dateien erst zu übernehmen (»git add«),

	10.2. dann ist die lokale Kopie des GitHub-Repositorii zu aktualisieren (»git commit -m«) und

	10.3. anschließend ist dieses hochzuladen: »git push«.

09. Wenn alle veränderten Dateien übernommen werden sollen: »git add *«, alternativ »git add NAME VERÄNDERTER UND HOCHZULADENDER DATEIEN«.
10. Aktualisierung lokaler Kopie des GitHub-Repositorii (»git commit -m "Beschreibung der vorgenommenen Änderungen"«)
11. Übernahme auf externes Git-Repositorum: »git push«
12. Wichtig: Nach dem ersten Herunterladen eines GitHub-Repositorii sollte man vor der Arbeit mit dieser lokalen Kopie dieselbe immer erst aktualisieren: »git pull«.
13. Für ein Verzeichnis der Befehle und damit verbundenen Möglichkeiten Git: »git help«.
14. Möglichkeiten sind eg:
	14.01. In entsprechendem Verzeichnis – in diesem Fall »ak-ocr« –: »git status«.
	14.02. Zur Anzeige der erfolgten Änderungen: »git diff«.
	14.03. »git branch -a«
14. Git kann auch benutzt werden, um ein Primärverzeichnis auf einem lokalen Rechner zu erstellen und so die Versionskontrolle für die nur lokal erstellten Dateien zu nutzen: dafür ist der Befehl »git init« in einem beliebigen Verzeichnis auszuführen.