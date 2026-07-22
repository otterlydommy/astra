---
description: Große/langwierige Aufgabe in gesicherten Etappen abarbeiten (schützt vor Verlust bei Absturz/Nutzungslimit)
---

Arbeite die vom Nutzer genannte Aufgabe so ab, dass ein Absturz oder ein erschöpftes Nutzungslimit **höchstens eine Etappe** kostet, nie den ganzen Fortschritt. Für rechen-/token-intensive Aufgaben, bei denen unklar ist, ob das Limit reicht.

Aufgabe (falls hier nichts steht: die zuletzt besprochene große Aufgabe): $ARGUMENTS

1. **Etappen planen (vor Beginn):** Die Aufgabe in kleine, je eigenständig abgeschlossene und einzeln verifizierbare Etappen zerlegen. Jede Etappe muss einen **konsistenten, in sich lauffähigen Zwischenstand** hinterlassen (kein Halbzustand als geplantes Ende). Lieber mehr kleine als wenige große Etappen. Die nummerierte Etappen-Liste als eigenen Abschnitt ins `04_Progress_Log.md` schreiben, bevor Etappe 1 startet — so überlebt der Plan einen Absturz.
2. **In-Session-Tracking:** Die Etappen zusätzlich als TaskList führen (eine Task pro Etappe), Status live pflegen.
3. **Nach JEDER fertigen Etappe — Checkpoint:**
   - a) Wenn Blender geändert wurde und das Working File geladen ist: `bpy.ops.wm.save_mainfile()` (stehende Freigabe D-024).
   - b) In der Etappen-Liste im Progress-Log die Etappe als „fertig (Datum/Zeit)" markieren und den nächsten Schritt notieren.
   - c) Ergebnis verifizieren, bevor die nächste Etappe beginnt (Messen statt Annehmen).
4. **Nur nach Freigabe umsetzen:** Betrifft eine Etappe Node-/Szenen-Änderungen (nicht nur Lesen/Messen/Speichern), gilt das normale Rollenmodell — Dommy setzt um bzw. gibt frei. `/etappen` ändert das Freigabe-Prinzip nicht; es sichert nur den Fortschritt.
5. **Bei Abbruch:** Der nächste Chat setzt mit `/fortsetzen` an der letzten als „fertig" markierten Etappe an.
6. **Abschluss:** Wenn alle Etappen fertig sind, den Etappen-Abschnitt im Progress-Log als erledigt kennzeichnen und den regulären `**Wiedereinstieg:**` schreiben.
