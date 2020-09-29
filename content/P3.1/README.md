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
