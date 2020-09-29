## **16 _Dez_** Server Request Verarbeitung

Ändern Sie den Servercode dahingehend, dass er statt einfach nur einem URL Bounce die in der URL (im query Teil / über eine GET Anfrage) übergebenen Variablen und Werte zunächst in ein Javascript Objekt / Assoziatives Array umwandelt, bzw diese aus der URL ausließt (s. `Url.parse()`). Geben Sie nun unter verschiedenen Pfaden die Informationen auf verschidene Weisen zurück:

- unter `/html` formatieren Sie die übergebenen Daten gut lesbar als HTML Text/Code. Dieser zurückgegebene HTML Code soll nun auf der Formularseite einfach als Antwort des Servers in die Seite ohne weitere Formatierungen eingebunden werden.
- unter `/json` formatieren Sie die übergebenen Daten als JSON Objekt und geben das zurück. Auf der Formularseite parsen Sie dieses in ein JS Objekt und geben dieses auf der Konsole aus. Vergleichen Sie (mit bloßem Auge) das Objekt welches Sie zurück bekommen haben mit dem Objekt das sie los geschickt haben. Wenn die Objekte gleich sind, haben Sie alles richtig gemacht.

Verlinken Sie beide Anfragen in einer HTML Seite, entweder über unterschiedliche Buttons bei gleichem Formular oder nutzen Sie zwei Formulare. Nutzen Sie weiterhin `fetch()` um Ihre Anfragen zu versenden und die Antworten zu empfangen, sonst können Sie die Antworten nicht auf ihrer eigenen Seite darstellen.

### Bonusaufgabe

Versuchen Sie, statt über GET über POST eine Anfrage zu verschicken und auszulesen. Legen Sie dazu am besten eine neue HTML Seite an, mit einem ganz simplen "Login" Bereich (Benutzername/Email, Passwort, Button). Verschicken Sie die Daten mit `fetch()`, lesen sie die Daten auf der Serverseite aus, und schicken Sie diese in einer gut formatierten Form zurück (um überprüfen zu können, dass die Daten auch wirklich angekommen sind). Alternativ können Sie die übergebenen Daten auch mit (vorher festgelegten) "korrekten" Logindaten auf der Serverseite überprüfen und dann stattdessen als Serverantwort das Ergebnis des Loginversuchs zurückgeben.

>### **Achtung!:** Beachten Sie die [<ins>Coding Style Guidelines</ins>](https://hs-furtwangen.github.io/GIS-SoSe-2020/codingstyle/). Code der diesen Guidelines nicht entpricht wird nicht akzeptiert! Code der W3 Errors oder JS-Errors aufweist wird ebenfalls nicht akzeptiert! Verstöße führen zu einer Ampelstufe 🚦
