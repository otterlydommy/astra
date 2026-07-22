---
description: Nach Absturz / Nutzungslimit / Chat-Wechsel den letzten Stand rekonstruieren und weiterarbeiten
---

Stelle den Arbeitsstand wieder her und mach dort weiter, wo zuletzt gesichert wurde. Wichtig: Ein Abbruch kann **mitten in einer Etappe** passiert sein — der Live-Zustand in Blender kann daher vom letzten Doku-Eintrag abweichen. **Nicht raten, sondern messen und abgleichen.**

*Arbeitsdatei, Doku-Dateien und Referenzwerk stehen im **Projektwerte-Block der `CLAUDE.md`**. Von dort holen — nicht aus dieser Datei, nicht aus der Erinnerung, und niemals aus einem Schwesterprojekt.*

1. **Session-Start ausführen** (siehe `CLAUDE.md`): BlenderMCP-Check (Version, `bpy.data.filepath`, Engine), dann die aktuelle Projektdoku lesen — neuester Fortschrittseintrag und offene Probleme.

2. **Wiedereinstiegspunkt lesen:** die letzte `**Wiedereinstieg:**`-Zeile im Fortschrittseintrag. War ein `/etappen`-Lauf offen, dessen Etappen-Checkliste heranziehen: welche Etappe war zuletzt als „fertig" markiert?

3. **Live gegen Doku abgleichen:** den in Blender gemessenen Ist-Zustand mit dem letzten dokumentierten Soll vergleichen. Drei Fälle:
   - **Deckungsgleich** — sauberer Wiedereinstieg, mit dem nächsten markierten Schritt fortfahren.
   - **Blender ist weiter als die Doku** (Etappe umgesetzt, aber nicht dokumentiert) — fehlende Doku nachtragen, dann weiter.
   - **Blender ist hinter der Doku / Halbstand** (Etappe brach mitten im Aufbau ab) — den unfertigen Teil benennen, Dominik entscheiden lassen, ob berichtigt oder neu ausgeführt wird, erst dann weiter.

4. **Falls der Chatverlauf teilweise vorhanden ist:** offene Zusagen und den zuletzt gelieferten Baustein daraus rekonstruieren. Es gilt trotzdem der **gemessene Live-Zustand** aus Schritt 3 als Wahrheit.

5. **Zusammenfassen:** in zwei bis drei Sätzen „Wir waren bei …, der Live-Abgleich ergab …, nächster Schritt ist …" melden, dann regulär weiterarbeiten. **Nur Abweichungen berichten**, keine Bestätigungsliste dessen, was ohnehin stimmt.
