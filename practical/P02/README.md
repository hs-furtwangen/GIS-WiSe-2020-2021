## **P2** TypeScript

In diesem zweiten großen Abschnitt des Praktikums werden wir uns ganz dem Einstieg und der Entwicklung mit Typescript widmen.

### Aufgabe

Hier sollte die Gesamtaufgabe kurz beschrieben werden.
Verweis auf die Etappen, die unten den einzelnen Praktikumsterminen zugeordnet sind.

### Abgabe zum 6. Dezember 2020

Per Kommentar im Github Issue _(Link folgt)_

---

## **6 _Nov_** Typescript und Javascript Einstieg

Diese Woche dient als Einstieg in die Entwicklung mit einer für Sie neuen Sprache, darum werden wir lediglich die Grundlagen behandeln. In der nächsten Woche geht es dann an konkretere Umsetzungen für die Abschnittsaufgabe.

### Aufgabe 1 - Basics

```ts
function a1(): void {
    let x: string = "Alles";
    console.log(x);
    func1();
    console.log("Logo!");
}

a1();

function func1(): void {
    console.log("Klar?");
}

```

**a)** Lesen Sie das obige Programm. Was wird wohl auf der Konsole ausgegeben? Lassen Sie das Programm laufen und experimentieren Sie mit den Namen der Variablen und Funktionen. Welche Variablennamen sind zulässig, welche nicht?  

**b)** Öffnen Sie im Browser den Debugger (neben der Konsole) und setzen Sie einen Breakpoint in Zeile 3 (alternativ können Sie im Code vor Zeile 3 das Schlüsselwort `debugger;` einfügen). Laden Sie dann die Seite neu und gehen Schritt für Schritt durch den Code durch, die Schaltflächen dafür sind normalerweise rechts am Rand:  
![](https://camo.githubusercontent.com/372a0f981e20eab3064ce57f78bf81a23c9808e2/68747470733a2f2f692e696d6775722e636f6d2f53566e4c5930702e706e67)



> ℹ️ Ein Debugger dient wie der Name schon vermuten lässt dem Debuggen, dem Entfernen von Bugs, dem Finden und Erkennen von Fehlern. Er erlaubt es einem, ein Programm zu pausieren und dieses dann Zeile für Zeile durchzuführen um den Ablauf und die Änderungen die während des Durchlaufs passieren, nachzuvollziehen. Diese langsame und Schritt für Schritt Vorgehensweise erlaubt es relativ einfach die internen Vorgänge nachzuvollziehen und Fehler in der Logik des Programms zu finden. Er ist also neben Konsolenausgaben das wichtigste und wertvollste Tool zur Fehlererkennung.

> > Der Name "Bug" stammt Gerüchten nach daher, dass in den ersten elektronischen Rechnern die mechanischen Kontake nicht mehr zusammengedrückt werden konnten, weil ein Käfer seinen Weg in den Zwischenraum gefunden hat, wodurch sich die Maschine verrechnet hat.

> ℹ️ Bei vielen Programmiersprachen ist der Debugger direkt in der IDE (in unserem Fall VSCode) integriert, aber um Javascript Code ausführen zu können benötigt man entweder einen Browser oder einen Server, was das Debuggen deutlich schwieriger macht. Glücklicherweise steht uns in Browsern ein Debugger zur Verfügung.

**c)** Fügen Sie weitere Funktionen ein, die wie `func1()` jeweils ein Wort ausgeben. func1 kann dafür kopiert und angepasst werden. Rufen Sie die Funktionen in `a1()` so auf, dass der Text "Alles Gute! Alles klar? Alles Logo!" auf der Konsole ausgegeben wird.

### Aufgabe 2 - Kontinuierliche Variablenmanipulation

```ts

function a2(): void {
    let i: number = 9;

    do {
        console.log(i);
        i = i - 1;
    } while( i > 0);
}

a2();

```

Schauen Sie sich den obigen Code an und versuchen Sie nur durch lesen zu verstehen was passiert. Was wird auf der Konsole ausgegeben? Wann verändert sich was?  
Lassen Sie den Code dann laufen und überprüfen Sie, ob sie richtig liegen. Schauen Sie sich den Programmablauf mit dem Debugger an. Fügen Sie außerdem im Debugger die Variable `i` zu den überwachten Variablen hinzu ("Watch" in Chrome, "Ausdruck beobachten" in Firefox), um deren Änderung einfacher zu verfolgen.


### Aufgabe 3 - Fehler erkennen und vermeiden lernen

**a)** Bauen Sie in dem Code von A1 und A2 Fehler ein (s. auch [Arten von Fehlern](../../#arten-von-fehlern)) und studieren Sie die Fehlermeldungen in VSCode. Lässt sich aus den Fehlermeldungen schließen, was falsch ist?

**b)** Tun sie sich mit Komilitonen zusammen und versuchen Sie die Fehler der anderen zu finden un zu lösen.

1.) Durch Codeinspektion: Versuchen durch Lesen die Fehler zu finden.  
2.) Durch Fehlermeldungen: Die Fehler in VSCode anschauen und versuchen, diese zu verstehen.  
3.) Durch Auskommentieren und Debugger: Wenn das Programm sich übersetzen lässt, aber nicht das richtige Verhalten aufweist, nach und nach Codeschnipsel aus und wieder einkommentieren, bis der Auslöser gefunden ist.  
4.) Wenn das alles nicht hilft, mit dem vorgegebenen Code vergleichen und die Fehler finden.

### Aufgabe 4 - Gobal vs Lokal

```ts
let x: string = "Hallo";
console.log(x);
func1(x);
console.log(x);
func2();
func3();
console.log(x);

function func1(y: string): void{
    y = "Bla";
    console.log(y);
}

function func2(): void{
    let x: string = "Blubb";
    console.log(x);
}

function func3(): void{
    x = "Test";
}
```

**a)** Betrachten Sie den obigen Code. Was wird er auf der Konsole ausgeben und warum? Lassen Sie ihn anschließend laufen und überprüfen Sie Ihre Annahmen.

**b)** Erklären Sie einem Komilitonen den Unterschied zwischen globalen Variablen, lokalen Variablen und Übergabeparametern.  
Inwiefern unterscheiden sich diese von Funktionen?

### Aufgabe 5 - Schleifen, Funktionen und andere Kontrollstrukturen

**a)** Schreiben Sie eine Funktion `multiply` welche zwei Zahlen als Parameter entgegen nimmt und als Rückgabewert das Ergebnis der Multiplikation der beiden Parameter liefert. Testen Sie Ihre Funktion auf eine geeignete Weise.

**b)** Schreiben Sie eine Funktion `max` welche zwei Zahlen als Parameter entgegen nimmt und die größere der beiden zurück gibt. Nutzen Sie dafür nicht `Math.max` sondern schreiben Sie ihre eigene Implementation. Testen Sie Ihre Funktion auf eine geeignete Weise.

**c)** Zählen Sie mithilfe einer `while` Schleife alle Zahlen von 1 bis 100 zusammen und geben Sie diese auf der Konsole aus.

**d)** Nutzen Sie eine `for` Schleife um 10 zufällige Zahlen auf der Konsole auszugeben. Nutzen Sie dafür [Math.random](https://developer.mozilla.org/de/docs/Web/JavaScript/Reference/Global_Objects/Math/math.random)

**e)** Schreiben Sie eine Funktion `factorial` welche eine Zahl `n` entgegen nimmt und als Rückgabewert die [Fakultät](https://de.wikipedia.org/wiki/Fakult%C3%A4t_(Mathematik)) (`1*2*3*...*n`) dieser Zahl zurück gibt. Nutzen Sie dafür eine Schleife (`while, do while, for`). Geben Sie außerdem `1` zurück, wenn `n` kleiner ist als 1.

**f)** Schreiben Sie eine Funktion `leapyears` welche alle Schlatjahre von 1900 bis heute auf der Konsole ausgibt. Ein Jahr ist ein Schaltjahr, wenn die Jahreszahl durch 4, aber nicht durch 100 teilbar ist. Sollte die Jahreszahl durch 400 teilbar sein, handelt es sich dennoch um ein Schaltjahr.

### Aufgabe 6 - Mehr Schleifen und Funktionen

**a)** Schreiben Sie eine Schleife welche auf der Konsole folgende sieben Zeilen ausgibt: 
```
#
##
###
####
#####
######
#######
```
_Hinweis: die Länge eines strings kann über `stringname.length` abgefragt werden._

**b)** Schreiben Sie ein Programm welches auf der Konsole alle Zahlen von 1 bis 100 ausgibt. Dabei gibt es zwei Ausnahmen: Ist die Zahl durch 3 teilbar, geben Sie statt der Zahl `Fizz` aus. Ist sie durch 5 (und nicht durch 3) teilbar, geben sie `Buzz` aus.  
_Hinweis: Nutzen sie den Modulo Operator `%` um zu prüfen, ob eine Variable durch eine andere teilbar ist (Rest 0)._

**c)** Nehmen Sie das Programm aus b) und modifizieren Sie es so, dass das Programm `FizzBuzz` ausgibt, wenn die Zahl durch sowohl 3 als auch durch 5 teilbar ist.  
_Hinweis: Dieser Teil der Aufgabe hat eine offensichtlichere und eine cleverere Lösung. Finden Sie beide?_

> Diese Frage ist eine beliebte Frage in Vorstellungsgesprächen. Wenn Sie diese also gelöst bekommen, ist Ihr Marktwert gerade gestiegen.

**d)** Schreiben Sie eine Funktion, welche einen String zurückgibt, der ein 8x8 Schachbrett repräsentiert, mit neuen Zeilen (`"\n"`) um die Zeilen zu trennen. An jeder Position im Brett ist entweder ein `#` oder ein Leerzeichen.

Wenn der String über console.log ausgegeben wird, sollte er etwa so aussehen:

```
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # # 
 # # # #
# # # # 
```

_Hinweis: Beginnen Sie mit einem leeren string (`""`) und fügen Sie dann immer mehr Zeichen hinzu. Für zwei Dimensionen brauchen Sie zwei Schleifen ineinander, eine für die Zeilen und eine für die Character innerhalb der Zeile._

**e)** Nehmen Sie die Funktion aus d) und fügen Sie ihr einen Übergabeparameter hinzu, welcher die Höhe und Breite des Brettes bestimmt. Schreiben Sie ihre Funktion so um, dass es mit jeder Größe Funktioniert.  
_Hinweis: Machen Sie sich Gedanken wie sie sich merken/berechnen können, welcher Character als erstes/nächstes in einer Zeile ausgegeben werden muss._

<!-- Überarbeiten Sie Ihren Shop aus Aufgabe 4 dahingehend, dass Sie die Artikel auf der Seite über TypeScript generieren.
Es sollten keine Artikel mehr im HTML direkt stehen, sondern durch TypeScript, nachdem die Seite geladen wurde, generiert werden.
Entwickeln sie dafür eine passende Datenstruktur über `interface`s, so dass alle artikelrelevanten Informationen (s. A4) in einem Array abgelegt, abgefragt und verwendet werden können. Legen Sie dann alle benötigten Informationen in Ihrem Code ab und generieren Sie über geeignete Schleife(n) nachdem die Seite geladen ist die Artikel dynamisch hinzu.
Wenn Sie können, trennen sie die Daten und die Funktionalität in unterschiedliche TS Dateien (ein gemeinsamer `namespace` ist  hier empfohlen). Beachten Sie die [Coding Style Guidelines](https://hs-furtwangen.github.io/GIS-SoSe-2020/codingstyle/).

**Klarstellung**: Das interface sollte einen Artikel abbilden, und sämtliche relevanten Artikelinformationen zu einem Artikel sollte in diesem Interface sinnvoll abgelegt werden können. Die Sammlung aller Artikel soll dann in sinnvoller Weise abgebildet werden, z.B. in _einem_ Array in dem alle Artikel liegen. Bedenken Sie dabei die Skalierbarkeit und Anpassbarkeit (wie schwierig ist es, einen Artikel hinzuzufügen/entfernen/ändern?)! Bei einer kleinen Änderung sollten Sie nicht mehr Änderungen an ihrem Code vornehmen müssen als die reine Information zu verändern. 

### Recherchehinweise:
[Auf DOM Elemente über JS zugreifen](https://www.w3schools.com/js/js_htmldom_elements.asp)  
[das HTML von DOM Elementen verändern](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)  
[Template Strings](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-1-4.html#template-strings)  

### Freiwillige Übungsaufgaben
[Übungsaufgaben mit Fokus auf Konsolenausgaben zum Selbststudium](https://github.com/Plagiatus/EIA/blob/master/Aufgaben.md) mit Lösungen. (Diese Aufgaben wurden ursprünglich für das Ende von EIA1 konzipiert um sich auf EIA2 vorzubereiten, stellen aber allgemein eine gute Ressource zum Selbststudium dar, inklusive einfacher Aufgaben zur Wiederholung als auch sehr komplizierte Aufgaben. _Keine offizielle Aufgabe, lediglich als Bonusmaterial wenn Sie Zeit und Lust haben noch etwas mehr zu üben!_) -->

---

## **13 _Nov_** Typescript und Javascript 77

????

## **20 _Nov_** Event Handling

>**Bei Problemen/Unklarheiten:** können Sie wie immer ins Praktikum kommen oder per Discord / Github Issues (/ EMail) Fragen stellen.

Erstellen Sie ein neues Verzeichnis und kopieren Sie die Dateien der letzten Aufgabe hinein. 

Die Aufgabe baut auf der Shop Aufgabe der letzten 2 Wochen auf. 

>**Empfehlung:** Sorgen Sie dafür, dass es nur 1 Shopseite mit allen Artikeln gibt, da Sie andernfalls auf allen Seiten auf denen Produkte angezeigt werden die Kriterien der Aufgabe 1 & Aufgabe 2 erfüllen müssen. 

Ziel der Praktikumsaufgabe ist es mithilfe von Events den Usern Ihres Shops eine bessere Interaktion mit der Website zu ermöglichen.

## Teilaufgabe 1

Registrieren Sie einen Klick-Event-Listener der die Maus-/Toucheingabe eines Users auf einen der Kaufen-Buttons detektiert. Beim Klick auf einen der Kaufen-Buttons soll über/neben dem Warenkorb (der Warenkorb **muss sichtbar bleiben**) z.B. in einem Kreis die Anzahl der geklickten Artikel angezeigt werden. Bei 0 Artikeln ist nichts sichtbar.

>**Anmerkung:** Denken Sie daran: Wenn Sie Code kopieren machen Sie etwa falsch. In diesem Fall sollte es nur eine einzige Funktion geben, welche dann von den Buttons aufgerufen wird, ggf mit passenden Übergabeparametern

### Beispiele aus echten Shops:

![Bsp. 1](buy_ex_2.PNG)
![Bsp. 1](buy_ex_1.PNG)
![Bsp. 1](buy_ex_4.PNG)
![Bsp. 1](buy_ex_3.PNG)

Berechnen Sie außerdem bei jedem Klick die Gesamt-Summe der Preise aller angeklickten Artikel und geben sie diese in der Konsole aus.  
Um das ganze sinnvoll zu gestalten, dürfen **nicht alle Artikel das Gleiche kosten**.

>**Anmerkung:** Ggf. müssen Sie Ihr Artikel-Interface aus der vorherigen Aufgabe so anpassen, dass der Preis nicht als string sondern als number gespeichert wird. Beachten Sie zwecks der Preisberechnung auch die Lösungshinweise weiter unten.

## Teilaufgabe 2

Anstelle von Sprungmarken (oder extra Seiten), die die Nutzer zu einer jeweiligen Kategorie bringen, sollen in der Navigationsleiste/Headdermenü/Hauptmenü per Klick-Event-Listener alle Artikel der "falschen" Kategorie ausgeblendet werden, sodass ausschließlich alle Artikel der geklickten Kategorie übrig bleiben. Des weiteren soll eine neue Option in der Navigationsleiste/Headdermenü/Hauptmenü ebenfalls per Klick-Event-Listener alle Artikel wieder einblenden. Dies bedeutet auch, dass die Artikel anderweitig ihren Kategorien zugeordnet werden sollten, statt über mehrere Arrays.

### Hinweise

>**Lösungshinweise** für beide Aufgaben  
Es gibt hier viele verschiedene Möglichkeiten, diese Probleme zu lösen. Hier sollen drei verschiedene Ansätze genannt werden, um Ihnen den Einstieg in die Aufgabe zu erleichtern:
> - _Abreißen und neu bauen_ - bei jeder Änderung der "Anzeigekriterien" entfernt man alle Artikel und erschafft nur die benötigten neu. Dies ist die einfachste Lösung, aber spätestens nächste Woche wird diese Probleme machen. Außerdem hilft sie nicht für Teilaufgabe 1.
> - _Informationen in HTML speichern_ - z.B. durch eigene Attribute die relevanten Informationen in den HTML Elementen selbst speichern. Dies ist zwar einfacher machbar, aber anfälliger für Änderungen (z.B. Preisänderungen) durch den Nutzer und folgt außerdem nicht dem Paradigma der Trennung von Funktionalität und Inhalt.
> - _Verbindung herstellen_ - irgendwie eine Verbindung zwischen den HTML Artikeln und den in JS abgelegten Daten über diese Artikel herstellen (z.B. über die indexierung des Arrays in dem die Artikel gespeichert sind). Die wahrscheinlich logisch komplexeste Lösung, aber dafür die sicherste und am besten für die kommenden Wochen geeignete Lösung.  

> Wir empfehlen dringend, dass Sie Ihre Lösungsidee zunächst auf dem Papier oder im kleinen Beispiel durchdenken und durchspielen, da es doch einige Stolperfallen gibt in die man sonst reinfallen könnte. **Diese Aufgabe ist nicht trivial!**

- mit [Element.setAttribute()](https://www.w3schools.com/jsref/met_element_setattribute.asp) und [.getAttribute()](https://www.w3schools.com/jsref/met_element_getattribute.asp) kann man einem Element eigene Atrribute hinzufügen und hinterher auch wieder abfragen.
- über das Event.target/currentTarget bekommt man zwar den Button zurückgeliefert, aber TS weiß nur, dass es vom Typ EventTarget ist. Somit können wir nicht auf die Eigenschaften von Node bzw. Element zugreifen, die wir brauchen. Wir können über die Typannotation dem TS versichern, dass wir wissen dass das EventTarget tatsächlich ein Element ist:  
```typescript
let target: HTMLElement = (<HTMLElement>_event.target);
// target.parentNode....
// target.getAttribute(...)...
```

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-WiSe-2020-2021/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße fürhen zu einer Ampelstufe 🚦

## Bonusaufgabe (keine Pflicht):

Implementieren Sie in der Navigation eine primitive Suchleiste die, optimalerweise mithilfe von RegEx, ansonsten mit String-Vergleichen, nach Übereinstimmungen sucht. Informieren Sie sich dafür über [RegEx](https://regexr.com/). Blenden Sie alle Items aus, in der weder in der Beschreibung noch im Titel eines Artikels ein Match gefunden wurde.

---

## **27 _Nov_** Event Handling 77

????

---

## **4 _Dez_** JSON, localStorage, Kommunikation

>**Bei Problemen/Unklarheiten:** können Sie ins Praktikum kommen oder per Discord/Mail fragen stellen.

Erstellen Sie ein neues Verzeichnis und kopieren Sie die Dateien der letzten Aufgabe hinein. 

Die Aufgabe baut auf der Shop Aufgabe der letzten 3 Wochen auf. 

Ziel der Praktikumsaufgabe ist es Daten über mehrere HTML Seiten hinweg speichern zu können. In dieser Aufgabe geht es darum zu speichern, welche Artikel von einem Kunden in den Warenkorb gelegt wurden. Außerdem sollen die auf der Website angezeigten Artikel per JSON geladen werden. 

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-WiSe-2020-2021/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦

### Teilaufgabe 1

Bisher werden Ihre Artikel über ein Array, welches direkt im Code liegt, eingelesen. Änderungen sind nur dann möglich wenn Sie das Array direkt bearbeiten. Ein besserer Weg ist es deshalb, die Daten und den Code voneinander zu trennen. Auf diese Art und Weise können jederzeit Artikel hinzugefügt oder aus dem Shop genommen werden, ohne dass der Code verändert werden muss.

Erstellen Sie eine JSON Datei mit allen Ihren Artikeln. Sie können dies von Hand oder mithilfe von online JSON Generatoren durchführen oder indem Sie folgenden Hinweis beachten.

>**Hinweis:** Damit Sie die JSON nicht von Hand befüllen müssen, können Sie mithilfe von `JSON.stringify(data_array)` aus Ihrem Daten-Array ein JSON Dokument erzeugen.

Lesen Sie nun die einzelnen Artikel, welche vorher in einem Array gespeichert waren aus der neuen JSON Datei aus. 

>**Hinweis:** Die `fetch()` Methode funktioniert nur auf Servern. Wenn Sie also wie gewohnt die HTML Datei nur lokal auf Ihrer Maschine in den Browser ziehen, funktioniert `fetch()` nicht. Verwenden Sie eine Live-Server Erweiterung in VSCode (besser) oder laden Sie Ihre Aufgabe für diesen Teil hoch (schlechter) & testen Sie dann.

Erzeugen Sie anhand der eingelesenen Daten die Artikel auf Ihrer Webseite.

>**Hinweis:** Es gibt mehrere Wege wie Sie die Kategorie eines Artikels in einer JSON Datei speichern können. Sie können z.B. jeden Artikel mit einer "Kategorie-ID" versehen und die Artikel beim Einlesen der JSON sortieren, falls Sie das noch nicht getan haben.

### Teilaufgabe 2

Verwenden Sie hierfür den [localStorage](https://www.w3schools.com/jsref/prop_win_localstorage.asp) (oder die Cookies). Wenn ein User der Website einen Artikel über einen der "Kaufen" Buttons in den Warenkorb legt, soll der jeweilige Artikel im local Storage gespeichert werden. 

Legen Sie eine Warenkorb Seite an (falls Sie noch keine haben). Auf der Warenkorb Seite werden alle Artikel die ein User per Button in den Warenkorb gelegt hat dynamisch per Code generiert und angezeigt. Auf der Warenkorb Seite wird außerdem der Gesamtpreis der Bestellung angezeigt. 

User haben die Mögkichkeit einzelne Artikel zu entfernen. Jeder dynamisch generierte Artikel hat einen "Entfernen/Löschen" Button/Text.

User können ihren gesamten Warenkorb löschen. Hierfür gibt es ebenfalls einen Button, der den localStorage leert & die Artikel aus dem Warenkorb entfernt. 

### Bonusaufgabe (keine Pflicht)

User können einen Artikel mehrmals in den Warenkorb legen (z. B. 5 Äpfel). Im Warenkorb kann die Anzahl der Artikel eines Typs geändert werden.
