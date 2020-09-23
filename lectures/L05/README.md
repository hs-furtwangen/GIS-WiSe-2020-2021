## **4 _Nov_** Typescript und Javascript

### Einrichtung Typescript in VSCode
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/05_Einrichtung_Typescript.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/05_Einrichtung_Typescript.mp4">Zum Video</a>
</video>

Denken Sie daran, immer wenn sie Ihren VSCode Editor öffnen, den BuildTask zu starten. Wenn Sie es automatisieren möchten, schauen sie eigenverantwortlich [hier](https://code.visualstudio.com/docs/editor/tasks) oder [hier](https://marketplace.visualstudio.com/search?term=Typescript%20Auto%20Compiler&target=VSCode&category=All%20categories&sortBy=Relevance).


`Strg + Shift + B` für die Build Tasks oder über `Terminal > Buildaufgabe ausführen`. Wählen sie "watch/Überwachen" um bis Sie VSCode schließen die js Dateien immer übersetzt zu bekommen oder "make/Erstellen" um einmal das gesamte Projekt zu übersetzen.

_Laden Sie die .js.map Dateien und selbstverständlich auch die .ts Dateien mit hoch._

**Links im Video**

- <a href="https://nodejs.org/">NodeJS</a>  
- [TSLint Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin)
- [Konfigurations Dateien (tsconfig & tslint)](https://github.com/hs-furtwangen/GIS-WiSe-2020-2021/tree/master/config_files)

**Terminal Befehle**
- `npm -v`
- `npm i -g typescript`
- `npm i -g tslint`
- `tsc --version`
  - falls es dabei in Powershell Probleme gibt, Powershell als Administrator ausführen, den folgenden Befehl ausführen und mit J/Y bestätigen.  
  `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine`

### Vorwort JavaScript / Typescript
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/05_JSTS_Vorwort.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/05_JSTS_Vorwort.mp4">Zum Video</a>
</video>

[Skript (PDF)](https://scheuerle.net/lehre/gis/scripts/05_JSTS_Vorwort.pdf)

### JavaScript / Typescript Einführung
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/05_JSTS_Einfuehrung.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/05_JSTS_Einfuehrung.mp4">Zum Video</a>
</video>


[Skript (PDF)](https://scheuerle.net/lehre/gis/scripts/05_JS_Einfuehrung.pdf)

### Typescript Kontrollstrukturen
<video controls width="100%"> 
    <source src="https://scheuerle.net/lehre/gis/videos/05_TS_Kontrollstrukturen.mp4" type="video/mp4"> 
    <a href="https://scheuerle.net/lehre/gis/videos/05_TS_Kontrollstrukturen.mp4">Zum Video</a>
</video>

[Skript (PDF)](https://scheuerle.net/lehre/gis/scripts/05_TS_Kontrollstrukturen.pdf)

### DOM Manipulation
<video controls width="100%"> 
    <source src="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_05_DOM_Manipulation.mp4" type="video/mp4"> 
    <a href="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_05_DOM_Manipulation.mp4">Zum Video</a>
</video>

### Typescript Dokumentation

[https://www.typescriptlang.org/](https://www.typescriptlang.org/)

---

## **?! _<small>Q&A</small>_** Fragen und Antworten

(die Publikation der Zusammenfassung erfolgt nach dem Q&A Termin)

Zusammenfassung von: [&lt;TawsTm&gt;](https://github.com/TawsTm)

### Fehler beim Kopieren von Aufgabencode?
Oft verwendet Prof. Rausch noch JavaScript. Hier fehlen manchmal Typisierungen, welche bei TypeScript notwendig sind. Bitte die Typisierung eigenständig hinzufügen. Ein Problem ist der Null-Error, wenn sich TypeScript nicht sicher ist, dass es den richtigen Typ verwendet. Das lässt sich durch Typaggregation beheben, d.h. in eckigen Klammern, vor dem Objekt, wird der Typ des Elements definiert (z.B. <HTMLDivElement>).

### Viel Code zu kopieren kann nicht richtig sein!
In CSS sollte man keinen Code kopieren! Im Normalfall gibt es dann eine bessere Lösung. Auch in den weiteren Aufgaben mit TypeScript ist oft kopierter Code ein Indikator für eine schlechte Lösung. 

### Namespace ist doch, um Variablen nicht im kompletten Code zu haben?
Namespace ist ein Namensraum, in dem die Variablen gültig sind. Ihr schreibt den Namespace einfach um euren kompletten Code und sonst ändert sich eigentlich nichts.

### VSCode zeigt einen Fehler an, aber hier sollte alles richtig sein?
Startet VSCode neu! In seltenen Fällen gibt es hier Fehler, die keine Fehler sind. Das lässt sich im Normalfall durch einen Neustart verbessern. Aber ihr könnt eigentlich davon ausgehen, dass Lint und VSCode fast immer recht haben 😉.

### Seid eigensinnig und fragt nach!
Wenn etwas nicht klar ist fragt einfach nach. Wir reißen euch nicht den Kopf ab, nur weil die meisten die Antwort vielleicht schon kennen.

### Wird das Aufgabenvolumen künftig weniger oder mehr?
An sich sind ab jetzt mehr programmatische Probleme zeitaufwändig. Es kann passieren, dass man etwas mehr Zeit benötigt, da man Fehler beheben muss und jeder einen bisschen anderen Ansatz hat. Wer gute Ansätze hat und von Grund auf sinnvoll programmiert, wird sich natürlich viel Zeit sparen.

### Auf dem Handy sieht meine Seite blöd aus aber im Browser gut?
Man kann den Debugger im Browser verwenden und so schon voreingestellte Mobile Devices als Darstellung verwenden. Dadurch lässt sich fast jedes gängige Handy simulieren.

### FlexBox vs. Grid, was ist besser?
Findet es für euch selbst heraus. Hier spalten sich ein wenig die Geister.

### Denkt zukunftsorientiert!
Man will nicht immer den kompletten Code überarbeiten, sondern z.B. einfach ein Element an einem Array anfügen und den restlichen Code nicht anfassen müssen.

### Variablennamen sollten aussagekräftig sein.
Der Name der Variable sollte darstellen, für was die Variable im Endeffekt steht.

### W3-Error: a-Tag sollte nicht mit Button verwendet werden?
Ein Button gehört eigentlich immer in ein Formular. Um trotzdem einen Button zu verwenden, kann ein Div-Element einfach wie ein Button gestylt und somit simuliert werden, ohne einen wirklichen Button zu integrieren.
