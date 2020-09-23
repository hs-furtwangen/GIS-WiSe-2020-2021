## **P3** Server & Datenbanken

Kurze Einleitung in die 3. Etape des Praktikums.

### Aufgabe

Hier sollte die Gesamtaufgabe kurz beschrieben werden.
Verweis auf die Etappen, die unten den einzelnen Proaktikumsterminen zugeordnet sind.

### Abgabe zum 1. November 2020

Wie? Wo?

---

## **9 _Dez_** Serveranbindung

### Teilaufgabe 1

Entwickeln Sie mit HTML Formularen eine einfache HTML Seite (z.B. ein Login, eine Addresseingabe, etc.) und lassen sie dieses Formular automatisch auf `https://gis-example.herokuapp.com` über GET verlinken.

Experimentieren Sie mit verschiedenen Input Elementen und den daraus erzeugten Werten. 

Folgen Sie außerdem der Erklärung zur Entwicklung mit NodeJS und setzen Sie sich einen online Server auf. Kopieren Sie als Server Code zunächst den **[Code des Beispielservers](https://github.com/Plagiatus/GIS_SoSe2020/blob/master/Aufgabe08/Server/server.ts)**. Sonst (bei z.B. einer leeren js Datei) wird ihr Heroku Server ständig die Datei starten und erwarten, dass sie weiterläuft, da sie sich aber direkt beendet (weil es ja nichts auszuführen gibt, bzw nichts gibt was auf irgendetwas anderes wartet), denkt er die Anwendung würde crashen.

(Diesen Teil müssen Sie _nicht_ auf Ihrem Steckbrief verlinken)

### Teilaufgabe 2

Schauen Sie sich den **[Code des Beispielservers](https://github.com/Plagiatus/GIS_SoSe2020/blob/master/Aufgabe08/Server/server.ts)** an, versuchen Sie zu verstehen was passiert und übernehmen Sie ihn in Ihr Repository. Kommentieren Sie sich die einzelnen Zeilen und beschreiben Sie, was was tut. Passen Sie den Request Handler so an, dass der query/path string nicht nur auf der Webseite, sondern auch in der Konsole des Servers ausgegeben wird.

Passen Sie ihre Formularseite aus Teilaufgabe 1 so an, dass sie statt automatisch über die eingebaute GET Anfrage des Formulars den Versand und Empfang der Daten über FormData selbst abwickeln. Verwenden Sie `fetch` um die Anfrage asynchron an den Server zu schicken und dann z.B. in der Konsole die Antwort des Servers auszugeben.

Entwickeln Sie dazu zunächst auf Ihrem lokalen Node Server, und ändern Sie vor der Abgabe dann den Link auf ihre Heroku App.

> **Hinweis**: Heroku schaltet seine gratis Server nach einigen Minuten ohne Anfragen aus und startet sie neu sobald eine Anfrage rein kommt. Darum kann es manchmal einige (10-15) Sekunden dauern, bevor die erste Antwort von Heroku geliefert wird.

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-SoSe-2020/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦

---

## **16 _Dez_** Server Request Verarbeitung

Ändern Sie den Servercode dahingehend, dass er statt einfach nur einem URL Bounce die in der URL (im query Teil / über eine GET Anfrage) übergebenen Variablen und Werte zunächst in ein Javascript Objekt / Assoziatives Array umwandelt, bzw diese aus der URL ausließt (s. `Url.parse()`). Geben Sie nun unter verschiedenen Pfaden die Informationen auf verschidene Weisen zurück:

- unter `/html` formatieren Sie die übergebenen Daten gut lesbar als HTML Text/Code. Dieser zurückgegebene HTML Code soll nun auf der Formularseite einfach als Antwort des Servers in die Seite ohne weitere Formatierungen eingebunden werden.
- unter `/json` formatieren Sie die übergebenen Daten als JSON Objekt und geben das zurück. Auf der Formularseite parsen Sie dieses in ein JS Objekt und geben dieses auf der Konsole aus. Vergleichen Sie (mit bloßem Auge) das Objekt welches Sie zurück bekommen haben mit dem Objekt das sie los geschickt haben. Wenn die Objekte gleich sind, haben Sie alles richtig gemacht.

Verlinken Sie beide Anfragen in einer HTML Seite, entweder über unterschiedliche Buttons bei gleichem Formular oder nutzen Sie zwei Formulare. Nutzen Sie weiterhin `fetch()` um Ihre Anfragen zu versenden und die Antworten zu empfangen, sonst können Sie die Antworten nicht auf ihrer eigenen Seite darstellen.

### Bonusaufgabe

Versuchen Sie, statt über GET über POST eine Anfrage zu verschicken und auszulesen. Legen Sie dazu am besten eine neue HTML Seite an, mit einem ganz simplen "Login" Bereich (Benutzername/Email, Passwort, Button). Verschicken Sie die Daten mit `fetch()`, lesen sie die Daten auf der Serverseite aus, und schicken Sie diese in einer gut formatierten Form zurück (um überprüfen zu können, dass die Daten auch wirklich angekommen sind). Alternativ können Sie die übergebenen Daten auch mit (vorher festgelegten) "korrekten" Logindaten auf der Serverseite überprüfen und dann stattdessen als Serverantwort das Ergebnis des Loginversuchs zurückgeben.

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-SoSe-2020/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦

---

## **13 _Jan_** Datenbanken Grundlagen

### Aufgabenteil 1
Gehen Sie die oben beschriebenen Schritte für eine lokale Mongo Installation durch.

### Aufgabenteil 2
Gehen Sie die oben beschreibenen Schritte für den Online Service durch und legen Sie dort eine Datenbank an. Experimentieren Sie auch hier mit Collections und Dokumenten, erstellen, manipulieren und löschen Sie mehrere davon. Kreieren Sie außerdem einen User für diese Datenbank, um darauf zugreifen zu können.

Als Abgabe verlinken Sie auf Ihrem Steckbrief einen Link auf die Web-Anwendung [https://mongodbnetbrowser.herokuapp.com/](https://mongodbnetbrowser.herokuapp.com/) und ergänzen sie diesen um die richtigen GET-Query-Parameter, so dass der Inhalt einer gut gefüllten Collection Ihrer mongodb.net/com-Datenbank beim Anklicken des Links angezeigt wird.

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-WiSe-2020-2021/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦

---

## **20 _Jan_** Datenbankzugriff über Server

Legen Sie eine HTML Seite an, auf der sich folgendes befindet:
- ein simples Formular (mit mindestens 3 verschiedenen Eingabefeldern)
- ein Bereich (z.B. ein div oder ein output) in dem eine Serverantwort angezeigt werden kann
- zwei Buttons die folgendes auslösen sollen:
  - Versand der im Formular eingegebenen Daten an den Server, welcher die Daten in Ihre remote Datenbank schreibt. (Bonus: leeren Sie das Formular danach)
  - Anfrage an den Server, die in der Datenbank gespeicherten Daten abzufragen und zurück zu geben. Die zurück gegebenen Daten werden im designierten Ausgabefeld als JSON String angezeigt. (Bonus: Formatieren Sie die zurückgegebenen Daten in sinnvoller Weise)
- (Bonus: Fügen Sie den ausgegebenen Objekten je einen Button hinzu, welcher es dem Nutzer erlaubt, die Daten wieder aus der Datenbank zu entfernen (natürlich wieder über eine Serveranfrage, welche dann die Daten wieder aus der Datenbank entfernt)).

#### Lösungshinweise:
- evtl kann es sinnvoll sein (besonders bei der Bearbeitung der Bonusaufgaben), den Code für die Datenbank auf dem Server in eine eigene Datei auszulagern.
- Testen Sie auf jeden Fall erstmal alles lokal, dann mit ihrer remote Datenbank, dann mit github pages.
- Testen Sie ausgiebig auch andere Datenbank-Funktionalitäten mit Ihrem Node Server, um ein Gefühl dafür zu bekommen, wie der Server mit der Datenbank kommuniziert, welche Rückgabewerte man bekommt, etc.

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-WiSe-2020-2021/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦
