## _V_ **2.3** DOM Manipulation und Event Handling

### Inhaltsverzeichnis

- [DOM](#dom)
  - [DOM Manipulation](#dom-manipulation)
  - [Baumstruktur](#baumstruktur)
  - [DOM Untersuchen](#dom-untersuchen)
- [Ereignisse](#ereignisse)
  - [Event Objekt](#event-objekt)
  - [Target](#target)
  - [Type](#type)
- [Event Handler](#event-handler)
  - [Handler-Implementation](#handler-implementation)
  - [Listener-Installation](#listener-installation)
- [Event Phasen](#event-phasen)
  - [Phase 1: Capture](#phase-1-capture)
  - [Phase 2: Target](#phase-2-target)
  - [Phase 3: Bubble](#phase-3-bubble)
  - [Listener-Options](#listener-options)
  - [CurrentTarget](#currenttarget)
  - [Path](#path)
- [Q&A](#-fragen-und-antworten)

### DOM
Lädt der Browser eine Datei und versucht diese als HTML-Datei zu interpretieren, baut er anhand der Daten im Speicher ein **Document-Object-Modell** (DOM) auf. Was schließlich im Browserfenster angezeigt wird, ist also nicht ein direktes Abbild der Datei, sondern ein Abbild dieses internen Speichermodells. 

Dabei wird aus den Elementen in der HTML Datei eine große Baumstruktur aufgebaut, bei der jeder Knoten ein Objekt ist, welcher einen Teil der Struktur repräsentiert, z.B. einen Titel, einen Absatz oder ein Bild.

![DOM Baum Beispiel](dom-tree.png)

> Erzeugen Sie eine einfache Textdatei mit der Endung ".txt" im Dateinamen und schreiben Sie einige Worte hinein, auch mit mehreren Leerzeichenfolgen, Umlauten und Tabulatoren. Laden Sie diese Datei im Browser und schauen Sie sich in den Entwicklertools die Seitenstruktur an (Tab links neben Console)   

Es wird deutlich, dass ein `html`-Element enstanden ist und darin ein `head`-Element sowie ein `body`-Element. In letzterem ist irgendwo, wahrscheinlich in einem `pre`-Element, unser eigentlicher Text vergraben.
> Ändern Sie die Endung in ".html" und laden Sie die Datei erneut. Was hat sich verändert?

Ein Skript kann das DOM manipulieren, darin Elemente verändern, hinzufügen oder löschen, der Browser kümmert sich automatisch um die Darstellung für den User. 

#### DOM Manipulation
<video controls width="100%"> 
    <source src="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_05_DOM_Manipulation.mp4" type="video/mp4"> 
    <a href="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_05_DOM_Manipulation.mp4">Zum Video</a>
</video>

#### Hinweise und Antworten auf potenzielle Fragen:

- Prof. Rausch verwendet of noch JavaScript in seinen Folien, wobei dann die typescriptspezifischen Typisierungen fehlen, welche von Ihnen ergänzt werden müssen. Meist kann VSCode vorschlagen, um welchen Typ es sich handelt. Hovern Sie dazu mit der Maus über das unterstrichene Wort.

>**Achtung:** Die Begriffe Objekt, Element und Knoten können teilweise synonym verwendet werden, es ist aber Vorsicht geboten. 'Alles' in Javascript/TypeScript ist ein Objekt, auch etwas vom Typ `number` oder `string`. Ein Knoten ist ein Objekt mit speziellen Eigenschaften und Fähigkeiten, mit dem sich ein Graph aufbauen lässt. Ein Element wiederum ist ein spezieller Knoten, der Eigenschaften eines HTML-Elementes aufweist.

Sehen Sie hier einen Ausschnitt aus der DOM Klassenhierarchie:

![Schaubild](DOM-Classhierachy.svg)

#### Baumstruktur
Das DOM lässt sich als Graph mit Knoten, die mit Kanten verbunden sind, darstellen.
> Suchen Sie die Klasse `Node` im Schaubild zur DOM-Hierarchie. Welche verwandtschaftlichen Beziehungen werden innerhalb der Klasse genutzt?  

Diese Knoten enthalten die Kernfunktionalität zur Bildung des Graphen und damit des DOMs. Jeder Knoten kann auf einen anderen Knoten als `parentNode` verweisen und auf eine Liste von `childNodes`. Im DOM ist `document` der Wurzelknoten, der lediglich eine Referenz auf `html` in seiner Kinderliste hat. `html` referenziert über die Eigenschaft `parentNode` das `document` und hat in seiner Kinderliste Referenzen auf `head` und `body`. `body` wiederum referenziert `html` als Mutter bzw Vater und hat wieder verschiedene Kindreferenzen, je nach Inhalt der darzustellenden Seite. Damit ergibt sich eine Baumstruktur, die sich in der Tiefe immer weiter verästeln kann und mit Hilfe der Entwicklertools, wie oben bereits getan, leicht einsehen lässt.

> Wählen Sie sich für ein besseres Verständnis des DOM aus Ihren eigenen vorangegangenen Arbeiten eine Seite aus und stellen Sie deren DOM grafisch dar.

#### DOM Untersuchen:

Sie können das DOM untersuchen und sich dessen Eigenschaften ausgeben lassen: 

##### DOM in Chrome untersuchen: 

![Dom in Chrome untersuchen](Chrome_DOM_Properties.PNG)

##### DOM in Firefox untersuchen: 

![DOM in Firefox untersuchen](Firefox_DOM_Properties_1.PNG)
![DOM in Firefox untersuchen](Firefox_DOM_Properties_2.png)
![DOM in Firefox untersuchen](Firefox_DOM_Properties_3.PNG)
![DOM in Firefox untersuchen](Firefox_DOM_Properties_4.PNG)


### Ereignisse
Das DOM bietet zudem ein System für die Interaktion mit dem Nutzer: das Eventsystem. Es stellt äußerst bequem Informationen zu Ereignissen innerhalb der Anwendung zur Verfügung, ohne dass Kenntnisse der Hardware erforderlich sind. Das Betriebssystem und der Browser werten diese Ereignisse bereits aus und bringen die Informationen darüber in eine allgemeine Form.

#### Event-Objekt
Events sind spezielle Objekte, die Informationen über ein Ereignis
tragen. Ein solches Ereignis kann ein Mausklick sein, ein Tastendruck, eine Berührung des Bildschirms, das Laden einer Datei oder die Beendigung einer Datenübertragung und vieles mehr.
> Im DOM-Klassendiagram sind einige Ereignisklassen aufgeführt. Finden Sie sie und heraus, welche Informationen diese tragen.

#### Kurze Zusammenfassung von Events:
<video controls width="100%"> 
    <source src="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_03_Events.mp4" type="video/mp4"> 
    <a href="https://lehre.gabriel-rausch.de/HFU/EIA1_SoSe20/L06/L06_03_Events.mp4">Zum Video</a>
</video>

#### Target
In der Regel bezieht sich ein Ereignis auf ein bestimmtes Objekt. Zum Beispiel auf den Button, der angeklickt wurde, den Link, der berührt wurde, das Fenster, das den Ladevorgang abgeschlossen hat oder das Textfeld, das verändert wurde. Die Eigenschaft `target` des Event-Objektes stellt eine Referenz auf dieses Ziel-Objekt zur Verfügung.
> Von welchem Typ ist `target`? schauen Sie im Klassendiagramm.  
> Objekte welcher Klassen / welches Typs können also `target`s sein? 

#### Type
`type` ist eine simple Zeichenkette und gibt an, was für ein Ereignis beschrieben wird. Hier sind beispielsweise die Werte `click`, `load`, `change`, `dragstart` und viele weitere vordefiniert. Es ist aber auch möglich eigene, neue Ereignisse zu definieren.  
> - Recherchieren Sie mehr. Finden Sie heraus, welche Arten von Events der Browser zur Verfügung stellt!

### Event-Handler
Handler sind Funktionen, die ein Ereignis auswerten. Der Umgang damit ist denkbar simpel.

#### Handler-Implementation
Um ein Ereignis auszuwerten, implementieren Sie einfach eine Funktion, deren Signatur diesem Muster entspricht:
```typescript
function handlerName(_event: Event): void {
    ...
}
```
Die Funktion nimmt also einen Parameter vom Typ `Event` entgegen, im Beispiel trägt dieser Parameter den Namen `_event`. Auch der Name der Funktion ist frei wählbar, es ist aber zu empfehlen den Prefix "handle" oder abgekürzt "hnd" zu verwenden, z.B. "handleClick", denn eine solche Funktion, die ein Event verarbeitet, nennt man Handler.

#### Listener-Installation
Damit das System weiß, bei welchem Ereignis welcher Handler aufgerufen werden soll, muss der Handler registriert werden. Dies erfolgt mit der Anweisung `addEventListener(...)`, zum Beispiel so:
```typescript
document.addEventListener("click", handleClick);
```
Der erste Parameter ist lediglich die Zeichenkette, die den Typ des Ereignisses beschreibt, der zweite eine Referenz zum Handler. Erhält das document-Objekt nun ein Event-Objekt vom Typ "click", wird dieses an die Handler-Funktion `handleClick` weitergeschickt. Das `document`-Objekt horcht also jetzt in das System hinein, es wurde ihm hierfür ein "Ohr" installiert, ein sogenannter Listener.
>**Achtung:** Ein häufiger Fehler in Javascript ist, statt der Referenz einen Funktionsaufruf zu implementieren, z.B. mit `addEventListener("click", handleClick())`. Die zusätzliche Klammer bewirkt, dass die Funktion bereits bei der Installation aufgerufen wird und deren zurückgeliefertes Ergebnis als Handler-Referenz installiert wird.

##### Beispiel
Das Folgende dürfte das wohl primitivste Beispiel sein, dass wir mit dem Eventsystem darstellen können. Eventuell müssen Sie zum Testen dieses Codes das `defer` Attribut des script tags weglassen.
```typescript
namespace L2_3_Load {
    window.addEventListener("load", handleLoad);

    function handleLoad(_event: Event): void {
        console.log(_event);
    }
}
```
Hiermit wird das `window`-Objekt, welches dem Browsertab entspricht in dem die Applikation läuft, angewiesen, die Funktion handleLoad aufzurufen, wenn ein "load"-Event ankommt, und ihr das zugehörige `event`-Objekt zu übergeben. `handleLoad` sorgt dann lediglich für die Darstellung des Objektes in der Konsole.
> - Untersuchen Sie das ausgegebene `event`-Objekt
> - Recherchieren Sie nach dem `load`-Event, wann genau wird es ausgelöst? Was ist der Unterschied zu `DOMContentLoaded` und dem `defer` Attribut für script tags?
> - Installieren Sie den Listener am `document`-Objekt, statt am `window`-Objekt. Was geschieht nun?
> - Experimentieren Sie in der gleichen Form mit `DOMContentLoaded`, wie verhält sich das System nun?

### Event-Phasen
Nicht alle Ereignisse werden allen Objekten im System mitgeteilt. Es ist also nur sinnvoll dort Listener zu installieren, wo sie auch wirken können. Besonders interessant wird das Ganze bei Nutzerinteraktionen, die auf DOM-Objekten ausgeführt werden, wie beispielsweise der Klick auf einen Button. Solche Ereignisse werden nämlich in drei Phasen durch den DOM-Graphen durchgereicht.

#### Phase 1: Capture
Das Event-Objekt wird zunächst an das `window` übergeben. Von dort wandert es zum `document`, zum `html`, zum `body` und weiter in den Baum in Richtung des `target`.
#### Phase 2: Target
Wenn es vom Elternobjekt zum `target` gereicht wird, befindet sich das Event-Objekt in der Target-Phase.
#### Phase 3: Bubble
Schließlich steigt das Event-Objekt im Baum wieder auf, bis es erneut das `window` erreicht. Es steigt also wie eine Luftblase unter Wasser an die Oberfläche.

#### Listener-Options
Bei der Installation des Listeners können mit einem dritten Parameter noch Informationen zur Funktionsweise mitgegeben werden. Wird hier schlicht ein `true` mitgegeben, reagiert der Listener auf die Capture-Phase. Ansonsten, was üblicher ist, auf die Bubble-Phase. In jedem Fall reagiert er auf die Target-Phase.

#### CurrentTarget
Neben dem `target` trägt das Event-Objekt auch noch eine Referenz auf das Objekt, dessen Listener das Ereignis als letztes gehört hat. Mit `currentTarget` kann also ausgewertet werden, wo sich das Ereignis gerade im DOM befindet und bearbeitet wird.

#### Path
Den kompletten Pfad, den das Event durch das DOM nimmt, kann man im Attribut `path` einsehen oder per Skript durch die Methode `composedPath()` ermitteln.

#### Beispiel
> - Untersuchen Sie die Seite [Phases](https://jirkadelloro.github.io/EIA2-Inverted/X00_Code/L02_Events/Phases/) und lassen Sie den Code laufen.
> - Was geschieht bei einem Klick auf den Button, bei einem Klick rechts daneben und bei einem Klick darunter? Warum?

### Takeaways

Sie haben gelernt:

- Wie Events in TypeScript funktionieren
- Wie die Phasen von Events verlaufen
- Wie Events registriert werden können
- Wie Eventhandling funktioniert
- Wie die DOM Klassenhierarchie aufgebaut ist 
- Wie DOM und Events zusammenhängen

### Typescript Dokumentation

https://www.typescriptlang.org/

---

## **?!** Fragen und Antworten

(die Publikation der Zusammenfassung erfolgt nach dem Q&A-Termin)

Zusammenfassung von: [&lt;Nutzername&gt;](https://github.com/)
