---
description: Nach Absturz / Nutzungslimit / Chat-Wechsel den letzten Stand rekonstruieren und weiterarbeiten
---

Stelle den Arbeitsstand von wawa_forge wieder her und mache dort weiter, wo zuletzt gesichert wurde. Wichtig: Ein Abbruch kann **mitten in einer Etappe** passiert sein — der Live-Zustand in Blender kann daher vom letzten Doku-Eintrag abweichen. Nicht raten, sondern messen und abgleichen.

1. **Session-Start ausführen** (CLAUDE.md): BlenderMCP-Check (Version, `bpy.data.filepath`, Engine) → `04_Progress_Log.md` (neuester Abschnitt) → `06_Known_Issues.md`.
2. **Wiedereinstiegspunkt lesen:** Letzte `**Wiedereinstieg:**`-Zeile im Progress-Log. Falls ein `/etappen`-Lauf offen war: dessen Etappen-Checkliste (im Progress-Log) heranziehen — welche Etappe war zuletzt als „fertig" markiert.
3. **Live gegen Doku abgleichen:** Den in Blender gemessenen Ist-Zustand (relevante Objekte/Materialien/Node-Groups/Settings der offenen Etappe) mit dem letzten dokumentierten Soll vergleichen. Drei Fälle:
   - **Deckungsgleich:** sauberer Wiedereinstieg — mit dem als Nächstes markierten Schritt fortfahren.
   - **Blender ist weiter als die Doku** (Etappe wurde umgesetzt, aber nicht mehr dokumentiert): fehlende Doku nachtragen, dann weiter.
   - **Blender ist hinter der Doku / Halbstand** (Etappe brach mitten im Aufbau ab): den unfertigen Teil benennen, Dommy die Berichtigung/Neuausführung dieser einen Etappe geben, erst dann weiter.
4. **Falls der Chatverlauf teilweise vorhanden ist:** offene Zusagen und der letzte gelieferte Baustein daraus rekonstruieren; trotzdem gilt der gemessene Live-Zustand (Schritt 3) als Wahrheit.
5. **Zusammenfassen:** In 2–3 Sätzen „Wir waren bei …, Live-Abgleich ergab …, nächster Schritt ist …" melden und regulär weiterarbeiten.
