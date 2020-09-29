## _P_ **1.4** CSS Vertiefung

Erstellen Sie eine Shopseite für Produkte ihrer Wahl. Versuchen Sie, etwas anderes zu verkaufen als Ihre Kommilitonen. Die Seite soll 
- visuell ansprechend sein. Achten Sie auf sinnvolle Verteilung der Artikel. (Holen Sie sich Inspiration zur Gestaltung gerne bei existierenden Shops)
- sich responsiv an die Bildschirmgröße anpassen (s.u.)
- mindestens 2 verschiedenen Kategorien auflisten, in denen insgesamt mindestens 12 Artikel sind.
- einen Headerbereich mit Namen, Logo, Icon für Einkaufswagen und Hauptmenü haben. Im Hauptmenü befinden sich die Namen der Kategorien mit Sprungmarken. Der Einkaufswagen darf auch im Hauptmenü sein, sollte sich aber visuell davon abheben (z.B. andere Farbe, gegenüberliegende Seite, etc). BONUS: Das Hauptmenü und der Einkaufswagen sind immer sichtbar.
- mindestens 6 (unterschiedliche) komplexe Selektoren verwenden

jeder Artikel soll
- mindestens einer Kategorie zugeordnet sein
- mindestens je ein/e/n Namen, Beschreibung, Bild und Preis besitzen
- in einem eigenen `<div>` Element gekapselt sein. (`<article>` is NICHT das richtige Element)
- einen "Kaufen/In den Einkaufswagen/o.ä." Button besitzen (welcher derzeit noch keine Funktion hat)

zu Responsiv:
- (mindestens) 3 Ansichten in denen der Shop gut aussehen und bedienbar sein muss: Desktop (>1024px), Tablet (600-1024px) und Mobil (<600 px).
  - in der kleinsten Ansicht sollten die Artikel wahrscheinlich am besten die gesamte Bildschirmbreite einnehmen.
- verwenden Sie (mindestens) 2 Media Queries
- verwenden Sie passendes Flussverhalten, bevorzugt Flexbox oder css-grid.
- stellen Sie außerdem natürlich sicher, dass das Hauptmenü und der Header allgemein auf allen Bildschirmgrößen gut verwendbar ist. Implementieren Sie ggf ein Burger Menu.

**TIPP**: Entwickeln Sie Ihre Seite so, dass entweder Mobil oder Desktop die Standardansicht sind, und überschreiben Sie die relevanten Auszeichnungen für die anderen beiden Ansichten.
In vielen Browsern können Sie automatisch verschiedene Bildschirmgrößen testen.
