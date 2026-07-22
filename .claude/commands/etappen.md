---
description: Große/langwierige Aufgabe in gesicherten Etappen abarbeiten (schützt vor Verlust bei Absturz/Nutzungslimit)
---

Arbeite die genannte Aufgabe so ab, dass ein Absturz oder ein erschöpftes Nutzungslimit **höchstens eine Etappe** kostet, nie den ganzen Fortschritt. Gedacht für rechen- und tokenintensive Aufgaben, bei denen unklar ist, ob das Limit reicht.

Aufgabe (falls hier nichts steht: die zuletzt besprochene große Aufgabe): $ARGUMENTS

*Arbeitsdatei und Doku-Dateien stehen im **Projektwerte-Block der `CLAUDE.md`**.*

1. **Etappen planen, vor Beginn:** Die Aufgabe in kleine, je eigenständig abgeschlossene und einzeln verifizierbare Etappen zerlegen. Jede muss einen **konsistenten, in sich lauffähigen Zwischenstand** hinterlassen — kein Halbzustand als geplantes Ende. Lieber mehr kleine als wenige große. Die nummerierte Liste als eigenen Abschnitt in die Fortschrittsdoku schreiben, **bevor** Etappe 1 startet, damit der Plan einen Absturz überlebt.

2. **Während der Sitzung:** die Etappen zusätzlich als Aufgabenliste führen (eine je Etappe) und den Status live pflegen.

3. **Nach jeder fertigen Etappe — Checkpoint:**
   - Wenn Blender geändert wurde und die im Projektwerte-Block genannte Arbeitsdatei geladen ist: speichern.
   - In der Etappen-Liste die Etappe als „fertig" mit Datum und Uhrzeit markieren und den nächsten Schritt notieren.
   - **Ergebnis verifizieren, bevor die nächste Etappe beginnt** — messen statt annehmen, Werte setzen und rücklesen in getrennten Calls.

4. **Nur nach Freigabe umsetzen:** Betrifft eine Etappe Szenen- oder Node-Änderungen (nicht nur Lesen, Messen, Speichern), gilt das normale Rollenmodell — Dommy gibt frei. `/etappen` ändert das Freigabe-Prinzip nicht, es sichert nur den Fortschritt.

5. **Bei Abbruch:** Der nächste Chat setzt mit `/fortsetzen` an der letzten als „fertig" markierten Etappe an.

6. **Abschluss:** Sind alle Etappen fertig, den Abschnitt als erledigt kennzeichnen, den regulären `**Wiedereinstieg:**` schreiben und committen.
