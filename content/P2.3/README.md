## _P_ **2.3** Event Handling

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
