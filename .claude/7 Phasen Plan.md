
Das ist eine neue Arbeitsumgebung. Es kann also sein, dass manche Verbindungen oder Verknüpfungen keinen Sinn ergeben, da sie von einer anderen Umgebung übernommen und anschließend per Hand bearbeitet wurden.

Verbinde dich mit dem geöffneten Blender 5.2 über das offizielle Blender-MCP. Das Add-on ist bereits installiert.
Scenne die complette Documentation
Stelle mir alle Fragen, die noch unklar sind.

Architektur-Review & Neuentwicklung einer reproduzierbaren, professionellen Blender-Produktionspipeline, die den visuellen Stil der animierten Streaming-Fernsehserie Arcane im League-of-Legends-Universum möglichst originalgetreu nachbildet. Das ausdrückliche Ziel ist nicht die Erstellung eines einzelnen Bildes, sondern die Entwicklung eines dokumentierten, modularen und wiederverwendbaren Systems bestehend aus NPR-Shader-Frameworks, Beleuchtung, Kamerasetup, Rendering, Compositing sowie Automatisierungs-Workflows.

Ziel
Architektur-Review & Neuentwicklung einer reproduzierbaren, professionellen Blender-Produktionspipeline, die den visuellen Stil der animierten Streaming-Fernsehserie Arcane im League-of-Legends-Universum möglichst originalgetreu nachbildet. Das ausdrückliche Ziel ist nicht die Erstellung eines einzelnen Bildes, sondern die Entwicklung eines dokumentierten, modularen und wiederverwendbaren Systems bestehend aus NPR-Shader-Frameworks, Beleuchtung, Kamerasetup, Rendering, Compositing sowie Automatisierungs-Workflows.
Bei Unklarheiten frage nach, bevor du Annahmen triffst.

Wichtige Einschränkung
Das Ziel ist nicht, die interne Rendering-Pipeline von Wuthering Waves exakt zu rekonstruieren. Da diese nicht öffentlich bekannt ist, soll stattdessen eine eigene, professionelle Blender-Architektur entwickelt werden, die den gleichen visuellen Eindruck möglichst originalgetreu reproduziert.
Prioritäten:
Visuelle Übereinstimmung mit der Referenz
Künstlerische Kontrolle
Modularität
Erweiterbarkeit
Wartbarkeit
Performance
Das Ziel ist ein produktionsreifes NPR-Framework – kein experimenteller Toon-Shader und keine Engine-Rekonstruktion.

Phase 1 – Referenzanalyse
Analysiere zunächst die Referenz.

Zu analysieren

Video
Convarcane Most Visually Stunning Scenes 4K Scaled 2X Prob-3, Esrgan Nvi 1.mp4
Geplanter Workflow
Analysiere das Video möglichst vollständig (idealerweise Frames im Abstand von ca. 0,5 Sekunden oder feiner, wenn notwendig).
Untersuche dabei insbesondere:
Kamera
Licht
Materialien
Shader
Schatten
Farben
Komposition
Rendering
Post Processing
VFX
Texturen
Geometrie
alle wiederkehrenden visuellen Regeln
Zusätzliche Analyse
Zerlege den Look systematisch in voneinander unabhängige Ebenen.
Level 0 – Bildsprache
Illustration / Digital Painting Charakter
Detaildichte
Formenvereinfachung
Farbphilosophie
Silhouetten
Level 1 – Beleuchtung
Key Light
Fill Light
Ambient Light
Bounce Light
Rim Light
Shadow Behaviour
Level 2 – Materialverhalten
Diffuse Response
Specular Response
Roughness
Subsurface
Transmission
Anisotropie
Level 3 – Stil-Shader
Toonisierung
Shadow Design
Highlight Design
Outline
Painterly Effekte
Level 4 – Post Processing
Bloom
Color Grading
Fog
Depth
Compositing
Level 5 – Assets
Modelle
UVs
Texturen
Geometrie
Ziel dieser Phase ist nicht nur zu beschreiben, wie das Bild aussieht, sondern zu bestimmen, welches System welchen Anteil am finalen Bild erzeugt.

Phase 2 – Ideale Architektur
Erst jetzt entwickelst du eine Architektur komplett von Grund auf.
Die Frage lautet ausdrücklich nicht:
Wie kann man mein Projekt verbessern?
Sondern:
Wie würde ein Senior Graphics Programmer heute ein langfristig wartbares NPR-Shader-System für Blender entwickeln?
Nutze dabei die offizielle Blender-Dokumentation sowie aktuelle Best Practices.
Optimiere auf:
Modularität
Erweiterbarkeit
Wartbarkeit
Performance
Wiederverwendbarkeit
klare Verantwortlichkeiten
Charakter-spezifische Anpassungen
Post Processing
Blender 5.2 LTS
Architekturprinzipien
Core Layer
Enthält ausschließlich universelle mathematische Funktionen.
Beispiele:
Light Evaluation
Shadow Calculation
Normal Processing
Color Management
Mask Operations
Keine Charakter- oder Materiallogik.
Material Layer
Verantwortlich für:
Skin
Hair
Eyes
Cloth
Metal
Leather
weitere Materialien
Materialien dürfen den Core verwenden, aber nicht verändern.
Character Layer
Enthält ausschließlich:
Face Shadow Maps
Character Masks
individuelle Anpassungen
Charakterparameter
Scene Layer
Enthält:
Licht
Atmosphäre
Kamera
Environment
Cinematic Layer
Enthält:
Shot-spezifische Anpassungen
Rendering
Compositing
VFX

Phase 3 – Non-Negotiables
Diese Anforderungen dürfen niemals verletzt werden.
Falls deine Architektur einen dieser Punkte nicht erfüllt, gilt sie als ungeeignet und Phase 2 beginnt erneut.
Shader
modular aufgebaut
Module austauschbar
langfristig erweiterbar
wiederverwendbar für verschiedene Charaktere
wiederverwendbar für verschiedene Materialien
Architektur
Keine Blackbox-Systeme.
Bevorzugt:
nachvollziehbare Node-Strukturen
dokumentierte Inputs
dokumentierte Outputs
klar definierte Verantwortlichkeiten
Vermeiden:
versteckte Automatismen
nicht nachvollziehbare Abhängigkeiten
unnötige Komplexität

Ziel des Frameworks
Entwickelt werden soll ein vollständig dokumentiertes, modulares Rendering-System für Blender.
Es soll den illustrierten Digital-Painting-Look möglichst originalgetreu reproduzieren.
Der Look soll wirken, als hätte ein Digital Artist jedes einzelne Bild über Monate hinweg von Hand gemalt.
Einzelne Frames sollen für sich betrachtet nicht von hochwertigen Manga-, Comic- oder Artbook-Illustrationen zu unterscheiden sein.
Das Endziel ist ausdrücklich nicht die Rekonstruktion einer einzelnen Szene oder eines einzelnen Standbildes.
Stattdessen soll ein langfristig wartbares Framework entstehen aus:
Shadern
Materialien
Beleuchtung
Kamera
Rendering
Compositing
unterstützenden Workflows
Dieses System soll den Stil konsistent auf beliebige Charaktere, Materialien, Environments und Lichtsituationen übertragen können, ohne für jede Szene oder jeden Charakter neu entwickelt werden zu müssen.

Phase 4 – Architektur-Review
Führe anschließend ein vollständiges Architektur-Review durch.
Hinterfrage jede Annahme und jede Entscheidung die du getroffen hast und ich in der documenation.
Arbeite den Entscheidungsbaum systematisch von oben nach unten ab.
Wenn eine Entscheidung auf einer anderen basiert, beginne immer bei der Grundlage.
Suche aktiv nach:
unnötiger Komplexität
versteckten Abhängigkeiten
technischen Schulden
Skalierungsproblemen
langfristigen Risiken
inkonsistenten Entscheidungen

Phase 5 – Entscheidungsprozess
Für jede Architekturentscheidung liefere immer:
Problem
Welche Fragestellung muss gelöst werden?
Empfehlung
Beschreibung
Vorteile
Nachteile
Risiken
Aufwand
technische Begründung
Bisherige Entscheidung
Beschreibung
Vorteile
Nachteile
Risiken
Aufwand
Alternative
Beschreibung
Vorteile
Nachteile
Risiken
Aufwand
Bewertung
Bewerte jede Lösung (1–10):
Look-Treue
Flexibilität
Wartbarkeit
Performance
Artist Control
Blender-Kompatibilität
Claude darf technische Empfehlungen aussprechen.
Die endgültige Entscheidung bleibt jedoch beim Nutzer.
Treffe keine Implementierungsentscheidung ohne ausdrückliche Freigabe.
Stelle jede Entscheidung einzeln mit Ankreuzfeldern vor.

Phase 6 – Validierung
Bevor Dokumentation geändert oder Code implementiert wird:
Erstelle einen Validierungsplan.
Definiere einen möglichst kleinen Prototyp zur Überprüfung der wichtigsten Architekturannahmen.
Beispielsweise:
ein Charakter
eine Szene
eine Lichtquelle
je ein Material pro Materialklasse
Teste unter anderem:
Tageslicht
Gegenlicht
farbiges Licht
harte Schatten
weiche Schatten
extreme Lichtfarben
Nahaufnahmen des Gesichts
Ziel ist es, Architekturentscheidungen möglichst empirisch zu überprüfen.

Phase 7 – Dokumentation
Erst nachdem sämtliche Architekturentscheidungen abgeschlossen und validiert wurden:
Dokumentation optimieren
alte Entscheidungen entfernen
Projektstruktur aufräumen
CLAUDE.md vereinfachen
Detailwissen in passende Dokumente verschieben
Redundanzen entfernen
Architekturentscheidungen nachvollziehbar dokumentieren
Vorher werden keine Dokumente verändert.

Arbeitsweise
Arbeite langsam und gründlich.
Qualität hat Vorrang vor Geschwindigkeit.
Hinterfrage jede Annahme.
Begründe jede technische Aussage.
Verifiziere Behauptungen, wenn möglich.
Kennzeichne Vermutungen eindeutig als Hypothesen.
Erfinde keine Sicherheit.
Wenn mehrere Lösungen sinnvoll sind, stelle sie objektiv gegenüber.
Schlage bei Unsicherheit kleine Experimente oder Prototypen vor.
Denke langfristig.
Priorisiere wartbare und nachvollziehbare Lösungen gegenüber kurzfristigen Optimierungen.
Wichtige Regel
Arbeite strikt phasenweise.
Beginne niemals automatisch mit der nächsten Phase.
Beende jede Phase mit:
einer Zusammenfassung,
offenen Fragen,
Unsicherheiten,
Empfehlungen für die nächste Phase.
Warte anschließend auf meine ausdrückliche Freigabe, bevor du fortfährst.
Änderungen am Projekt, an Dateien oder an der Dokumentation erfolgen ausschließlich nach meiner ausdrücklichen Zustimmung.
```
