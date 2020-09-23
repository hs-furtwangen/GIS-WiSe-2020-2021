## **14 _Okt_** HTML5 Familie

### HTML Audio und Video
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/02_GIS-EIA1-HTML-AV.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/02_GIS-EIA1-HTML-AV.mp4">Zum Video</a>
</video>

[Skript](https://scheuerle.net/lehre/gis/scripts/02_GIS-EIA1-HTML-AV.pdf)

---

### HTML Weiterführend
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/02_HTML_Weiterführend.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/02_HTML_Weiterführend.mp4">Zum Video</a>
</video>

- [Elemente Übersicht](https://wiki.selfhtml.org/extensions/Selfhtml/example.php/Beispiel:HTML-Kategorien.html)
- [W3C Validierer](http://validator.w3.org/)
- [Elemente Liste](https://developer.mozilla.org/de/docs/Web/HTML/HTML5/HTML5_element_list)


---

### Inspektor und Browserunterschiede
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/02_Inspektor_Browserunterschiede.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/02_Inspektor_Browserunterschiede.mp4">Zum Video</a>
</video>

- [caniuse](https://caniuse.com)

---

### Sie haben in dieser Lektion folgendes gelernt:
- Sie haben verstanden wie Sie den Inspektor ihres Webbrowsers verwenden können (Rechtsklick + Element untersuchen)
- Unterschiede zwischen Browsern
- Sie sind mit der grundlegenden HTML5 Seitenstruktur vertraut
  - Head/Body/Header/Main/Footer/Nav
  - Logische Verschachtelung (Inline / Block)
  - W3 Validierer
- Sie haben sich mit den folgenden HTML5 Elementen vertraut gemacht
  - header, main, footer
  - section, aside, article
  - table
  - list
  - form
  - div
  - Attribute / Eigenschaften: id, class, style, title, etc…
- Sie kennen sich mit HTML Audio und Video aus
  - gängige Audio- und Videoformate
  - Internet Media Types (MIME)
  - Datendurchsatz von Audio- und Videostreams

---

## **?! _<small>Q&A</small>_** Fragen und Antworten

Zusammenfassung von: [&lt;TawsTm&gt;](https://github.com/TawsTm)

### Gehören Footer zur HTML Dokument Grundstruktur?
Head und Body sind Grundstruktur, alles darin sind Strukturierende Elemente, aber in einem anderen Sinn. 

### Welche Einheiten soll man für die Attribute Height und Width benutzen?
Das Attribut Width und Height sind automatisch Pixel. Grundsätzlich (sobald erlaubt) solltest du alles in CSS machen, d.h. du kannst alles verwenden. Relative Werte sind im allgemeinen besser als feste, um die Seite responsive zu halten.

### Breaktags. Wie bekomm ich gute Anker hin?
Einfach nicht so viele Gedanken über gutes runterspringen machen. In der letzten Aufgabe gab es nur durch füllende Elemente eine schöne Lösung für das Problem. 
Breaktags braucht man im Normalfall nicht mehr. Wir verwenden später das CSS Box-Modell um die Abstände so hinzubekommen wie wir das wollen.

### Wie werden Sternchen verteilt und was bringen Sie?
Sterne gibt es für besondere Leistungen. Es gibt dadurch keine Vorteile außer Prestige. Drei Sterne pro Person sind maximum. Sterne bleiben nicht für andere Fächer bestehen.

### Dürfen wir veraltete HTML Tags verwenden?
Nicht HTML5 konforme Tags wie <font> oder ähnliche sollen und können in manchen Fällen nicht mehr verwendet werden.

### Ist das name-Attribute obsolet / wird es noch verwendet?
Das name-Attribut wird vor allem in Forms verwendet, um bei einer Submission eines Elementes einen Identifier zu diesem Element zu haben. In der Aufgabe sollte stattdessen das ID-Tag verwendet werden, da dieses später die eindeutige Zuweisung zu CSS-Code ermöglicht.

### Darf man für ein IFrame JavaScript und CSS verwenden?
Sie müssen bei einem IFrame nicht mit CSS und JavaScript arbeiten. Wenn das IFrame CSS und JavaScipt enthält, ist das halt so.

### Warum sollen die Aufgaben kopiert und nicht weiterbearbeitet werden?
Alte Aufgaben sollen nicht überschrieben werden, damit man auf den alten Inhalt noch zugreifen kann (Bitte kopieren und nicht alte Dateien in den neuen Ordner verschieben). 

### Warum ist alles gleich wie bei EIA1?
Sobald es richtig an die Programmierung geht, werden wir uns splitten. Da wir die rudimentären Grundlagen der Programmierung im Gegensatz zu den EIA1-Studierenden schon können, wird es hier zu unterschieden innerhalb der Lernmaterialien kommen.

### Kann man Dateien, die man nicht commiten möchte in Visual-Studio Code ignorieren?
Mit der .gitignore-Datei lassen sich Dateien und Ordner ignorieren. Ganze Ordner listet man in der .gitignore im Normalfall ohne Dateiendung einfach untereinander.
