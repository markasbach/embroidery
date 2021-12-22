embroidery - Stick-Dateien sinnvoll bearbeiten
==============================================

für Miriam

Dieses Projekt ist der Versuch, einen Überblick über (für macOS/Linux/iOS) verfügbare
Software-Werkzeuge zu bekommen, um Stickdateien zu bearbeiten. Dabei liegt der Fokus
zunächst darauf, grundlegende Bearbeitungsschritte wie die Auswahl der Stickfarben o.ä.
durchführen zu können, um z.B. heruntergeladene Stick-Dateien für weniger Farben umzuarbeiten.

Die im Internet direkt verfügbaren Informationen sind dürftig und teilweise veraltet,
weswegen hier einfach der Stand der Recherche von Dezember 2021 zusammengefasst und ggf.
ein Ausblick und Projektideen daraus abgeleitet werden.

Als Einstieg sei hier die Dokumentation zum Projekt PEmbroider zitiert, ein Projekt, das
im März 2020 in der ersten Pandemie-Welle entstanden ist:

> As this comparison of embroidery software shows, existing software for the creation 
> of custom embroidery designs frequently costs thousands of dollars; is rarely cross-platform; 
> and is almost never open-source. The free and open-source tools which do exist are either 
> full-featured standalone GUI tools (Ink/Stitch, Embroidermodder) or large-scale libraries 
> (EmbroidePy)—neither of which integrate easily with popular "creative coding" toolkits, 
> nor easily allow for the creation of generative and computational designs.

Das stimmt auch Ende 2021 noch immer. Gefunden habe ich tatsächlich dieselben Tools:

- InkStich
- Embroidermodder (2)
- EmbroidePy
- PEmbroider


InkStich
--------

https://inkstitch.org

InkStich ist ein Plugin für InkScape, wodurch ein vollständiges Zeichenwerkzeug mit
Import- und Export-Funktion für diverse Formate existiert.

Seit Mai 2021 ist Version 2.0 released, die mit InkScape 1.0 zusammen funktioniert.

Die Installation ist problemlos (es muss ein spezieller Schritt im Terminal beachtet werden)
und alles funktioniert wie beschrieben.


EmbroiderModder
---------------

http://embroidermodder.org
https://github.com/Embroidermodder

Das Projekt ist schon etwas älter, war aber mal sehr populär. 2014 gab es eine Kickstarter-
Kampagne, ein Jahr später ist die Arbeit aber eingeschlafen. 2021 sind wieder Code-Änderungen
auf github zu finden und ein neuer Plan, der in einem Release im Juli 2022 resultieren soll.

Ende Januar 2021 soll die Arbeit an libembroidery (der Kernfunktionen) abgeschlossen sein, 
danach wird am eigentlichen GUI-Programm gearbeitet.

Das Projekt enthält auch eine iOS-App, die ist aber rudimentär und total veraltet. Was auch
immer daraus wird - es braucht wohl etwas Geduld.


EmbroidePy
----------

https://github.com/EmbroidePy/pyembroidery
https://github.com/EmbroidePy/EmbroidePy
https://github.com/EmbroidePy/MaKe-stitch

Ein Python-Projekt (und ein Java-Schwesterprojekt), das einen Python-Bibliothek anbietet,
mit der alle möglichen Stick-Formate gelesen und geschrieben sowie mittels Code bearbeitet
werden können. Orientiert sich an libembroidery aus dem Embroidermodder-Projekt.

Es gibt auch ein sehr simples Programm, dass unter Windows, Mac, Linux läuft
und mit dem man Dateien laden, speichern, und minimal bearbeiten kann. Zu den Bearbeitungs-
Schritten zählen Rotation, Vergrößerung und Verkleinerung, aber auch ein Zugriff auf alle
Stiche in Form einer Tabelle. Komfortabel ist es nicht, aber man kann damit alle möglichen
Formate an Stick-Dateien anschauen und in andere Formate konvertieren. Die Installation ist
super simpel, sofern "pipx" installiert ist (ein Python-Programm-Manager).

    pipx install embroidepy

Dazu gehört ebenfalls ein Kommandozeilen-Werkzeug, mit dem Dateien auch in großer Anzahl
konvertiert werden können, sowie MaKe-Stich, mit dem Stickdateien Stich für Stich bearbeitet
bzw. erzeugt werden können. Das aktuell allerdings nur für Brother-Format "*.pmv".

Ebenfalls dazu gehört ein Plugin für das Tool "vpype" mit dem Vektrografiken für Plotter
aufbereitet werden können.

Der Code der GUI-Tools (embroidepy und MaKe-Stich) ist sehr kompakt, recht sauber, aber 
nicht dokumentiert und kommt ohne Tests. Daraus kann man aber mit kompaktem Aufwand etwas machen.


PEmbroider
----------

https://github.com/CreativeInquiry/PEmbroider

Dieses Projekt ist das neueste von allen. Es richtet sich vor allem an "Maker", die nicht
aus klassischen Programmiersprachen kommen, aber selber etwas programmieren wollen. Dazu
setzt das Projekt auf die Programmierumgebung "Processing", genau wie Arduino und ähnliche
Werkzeuge (Mark macht mit Processing auch das Prototyping für die LED-Matrix).

**Man kann mit PEmbroider keine Stickdaten laden** sondern nur erzeugen. Das entweder, indem
man selbst eine Grafik "Programmiert" (aus Linien, etc.), oder indem man Vektor- oder Pixel-
Bilder lädt (SVC und PNG).

Die Installation funktioniert (wenn man der Anleitung für manuelles Installieren des Plugins
in Processing folgt). Es sind Demos enthalten.


Fazit
-----

- Zum Konvertieren und/oder schnellen Anzeigen von Stick-Dateien ist das Mini-Python-Tool
`embroidepy` eine super einfache und schnelle Wahl.
- Soll eine Stick-Datei wirklich bearbeitet werden, geht das wohl am besten mit InkStich.
- Mit wenig Arbeit könnten die `EmbroidePy`-Werkzeuge schon zu etwas nützlichem umgebaut
  werden, denn der Python-Code ist sehr aufgeräumt und kompakt.
- Mit etwas mehr Arbeit könnte man 2022 eine macOS/iOS/iPadOS-App mit `libembroidery` starten.
