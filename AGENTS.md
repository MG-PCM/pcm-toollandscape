# Toolbox-Toollandschaft

## Aufbau

- Die Seite ist eine statische HTML-Datei mit eingebettetem CSS und JavaScript. In der lokalen Kopie liegt sie als `index.html` vor, im Site-Repository als `dist/index.html`. Halte die Seite offline und per Doppelklick nutzbar. PNG und SVG liegen neben der HTML-Datei und werden relativ verlinkt.
- `seed.tools` und `seed.links` bilden den Basiskatalog. Verwende stabile IDs und hinterlege Beziehungen als `[Quelle, Ziel, Status, Beschreibung]`. `active` steht für bestehende, `planned` für geplante oder teilweise umgesetzte Verbindungen. Dokumentiere offene Schnittstellen ausdrücklich.
- `renderGraph()` zeichnet die Ebenen Toolverteilung, Datenhaltung, KI-Dienst, Tools, Gateways sowie Geräte und Systeme. Anwender-Tools sind alphabetisch sortiert. Sammelleitungen bündeln Zugriffe auf dasselbe Ziel. Punkte kennzeichnen Verbindungen, Kreuzungen ohne Punkt bleiben getrennt. Geplante Verbindungen sind gestrichelt.

## Änderungen

- Ergänze bei neuen Knoten die sichtbare Position, das Symbol und die benötigten Leitungen. Prüfe Sammelleitungen, Kreuzungen und Beschriftungen auf Überlagerungen. Unterscheide Lesen, Schreiben und Verwaltung fachlich. LabAssist verwaltet beispielsweise `LabAssist.db`, LiveData liest daraus.
- Berücksichtige gespeicherte Kataloge in `localStorage`. Ergänze neue Basisknoten und Beziehungen bei der Migration und erhalte eigene Tools und Verbindungen. Prüfe den JSON-Import über `validate()` und verwende `escapeHtml()` beim Einfügen dynamischer Texte in HTML oder SVG.
- `marketingFrame()` ergänzt dasselbe Diagramm um Kennzahlen und Nutzen. Behalte Erfassungszeitraum und Zählgröße bei. Zeige neue Werte zuerst und alte in Klammern. Markiere Schätzungen mit `≈` und halte ihre Berechnungsgrundlage fest.
- Verwende englische Namen für Variablen und Funktionen. Schreibe Kommentare auf Deutsch und erkläre darin fachliche Entscheidungen oder Zusammenhänge, die aus dem Code allein schwer erkennbar sind.

## Prüfung vor der Weitergabe

- Wähle Prüfungen passend zum Änderungsumfang; führe nicht bei jeder Änderung einen vollständigen UI-Test durch. Prüfe UI-Verhalten gezielt, wenn es geändert wurde oder sich nicht anderweitig zuverlässig absichern lässt. Manuelle UI-Tests kann der Anwender übernehmen, wenn sie schneller oder zweckmäßiger sind.
- Prüfe bei Änderungen am Katalog den Import beziehungsweise die Migration eines älteren Datenstands. Erzeuge nach sichtbaren Diagrammänderungen die betroffenen Standardexporte `toolbox-architektur.{svg,png}` und `toolbox-marketing.{svg,png}` aus der vollständigen Ansicht ohne ausgewählten Knoten. PNGs werden in doppelter Auflösung gerendert.
- Prüfe die Marketingansicht und ihre Downloads nur, wenn Marketingansicht oder Downloads geändert wurden. Bei Änderungen am Export prüfe den betroffenen Pfad, insbesondere direkten Dateidownload oder dynamischen Export; der Export soll den vollständigen Stand zeigen und die aktuelle Auswahl in der Ansicht erhalten.
