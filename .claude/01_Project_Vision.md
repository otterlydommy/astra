# 01 – Project Vision

---

## 1. Zweck

Dieses Dokument ist der Einstiegspunkt der gesamten Produktionsdokumentation.

## 2. Ziel

### 2.1 Endziel

Eine **reproduzierbare, professionelle Blender-Produktionspipeline**, die den visuellen Stil der animierten Streaming-Fernsehserie **Arcane** im **League-of-Legends-Universum** möglichst originalgetreu nachbildet – einen Look, der wirkt, als hätte ein Digital Artist jedes einzelne Bild über Tage hinweg von Hand gemalt. Einzelne Frames sollen visuell nicht von hochwertigen Comic-, Manga- oder Artbook-Illustrationen zu unterscheiden sein.

Das Ziel ist ausdrücklich **nicht** die Erstellung eines einzelnen Bildes, sondern die Entwicklung eines dokumentierten, modularen und wiederverwendbaren Systems aus **NPR-Shadern**, Beleuchtung, Kamera, Rendering, Compositing und Automatisierungs-Workflows, das diesen visuellen Stil konsistent auf **jeden Charakter, jedes Environment und jede Lichtsituation** überträgt.


**Ziel-Look vs. Kalibrierbasis (wichtig, nicht verwechseln):**
- **Ziel-Look (Messlatte):** „Dawn Arrives"/Cartethyia — analysiert in `07_Reference_Analysis.md` §6–§8. Die Story-Cinematic fährt den gemalten Look am stärksten aus (weiche Ramps, malerische Kanten, kräftiges Compositing).

### 2.2 Teilziele


### 2.3 Nicht-Ziele (Scope-Abgrenzung)

- **Kein Patchen fremder Shader:**
- **Kein Quick-Look:** Kurzfristige visuelle Nähe durch undokumentierte Hacks widerspricht dem Portfolio-Anspruch (Eigenautorschaft, Nachvollziehbarkeit).

### 2.4 Erfolgskriterien

1. **A/B-Bestehen:** Renderings bestehen den Seite-an-Seite-Vergleich gegen Referenzframes der Originals
3. **Reproduzierbarkeit:** Ein zweiter Blender Artist kann Pipeline und Shader allein anhand dieser Dokumentation aufbauen und erweitern.
4. **Wiederverwendbarkeit:** Ein zweiter Charakter lässt sich ohne Strukturänderung am Framework anbinden (nur Material-Wrapper und Parameterwerte neu).

## 2A. Visuelle Designphilosophie — der illustrierte Look


## 2B. Technische Kern-Strategie (Shader · Material · Licht)


## 2C. Pipeline & technische Architektur


## 2D. Prozess, Qualität, Roadmap & Forschung

**Workflow & Arbeitsweise (bestätigt).** Standard-Ablauf *Analyse → Bewertung → Verbesserung → Planung → Umsetzung (nur nach Freigabe) → Validierung → Dokumentation*. Rollenmodell: Dommy setzt in Blender um/gibt frei, Claude analysiert/plant/verifiziert/dokumentiert (MCP default read-only). Baustein-Lieferung im Format „Bau-Liste + Erklärblock" (D-013). Verlust-Schutz über `/sichern` · `/fortsetzen` · `/etappen`

**Qualitätsstandards.** (1) **A/B-Bestehen** gegen Referenzframes **Verifikation vor Fortschritt**: jeder Baustein per MCP gemessen, bevor der nächste beginnt (messen statt raten). (4) **Reproduzierbarkeit/Wiederverwendbarkeit** (Erfolgskriterien 3/4): zweiter Artist baut allein aus der Doku; zweiter Charakter ohne Strukturänderung. (5) Keine Magic Numbers, Debug-Outputs Pflicht (Pfeiler 5).

**Dokumentationsstruktur.** Schlankes Set `00–07` (D-006) bleibt; Rollen: **01 = Master-Strategie/Einstieg** (dieses Dokument), 00 Rules, 02 Registry, 03 Shader-Architektur (v2), 04 Progress-Log, 05 Decisions, 06 Issues, 07 Reference-Analysis (Messbasis, §1–§14). Empfehlung: 07 wächst stark — bei weiterem Wachstum später nach Cluster splitten (nicht jetzt). Kein neues Dokument für die Strategie (in 01 integriert).

**Roadmap & Prioritäten (aktualisiert — Compositing vorgezogen).** Detailinhalte je Baustein in `03_Shader_Architecture.md` §5:

| # | Baustein | Kern | Priorität-Änderung |


## 3. Aktueller Stand

## 4. Technische Beschreibung

| Komponente | Festlegung |
|---|---|
| Blender | **5.2. LTS**
| Live-Anbindung | BlenderMCP (Analyse, Verifikation, Rendering; Änderungen nur nach erlaubniss) |
| Architekturprinzip | Modulare Node-Groups, Prefix `NPR_`, Material-Wrapper pro Materialklasse (Skin, Hair, Cloth, Metal)

**Rollenmodell (verbindlich):** Dommy setzt sämtliche Änderungen in Blender selbst um. Claude arbeitet analysierend, beratend und verifizierend; direkte Änderungen über MCP ausschließlich nach expliziter erlaubniss gefolgt von vollständiger Änderungsdokumentation und Prüfanleitung.

## 5. Designentscheidungen (nicht verhandelbar)

Diese Prinzipien sind die Existenzbegründung des Eigenbaus. Jeder Vorschlag, jeder Baustein und jedes Review wird gegen sie geprüft. Historie und Begründungen:

1. **Einfachheit & Transparenz:** Einfache Lösungen vor Over-Engineering. Keine Magic Numbers – jede Konstante erhält einen benannten Input oder einen Kommentar-Frame. Debug-Outputs für Kernstufen sind Pflicht (Test-Sphere-Workflow).

## 6. Bekannte Probleme

Vollständige, priorisierte Liste mit Status: `06_Known_Issues.md`


## 7. Offene Punkte (O-Nummern, Stand 2026-07-13)


## 8. Verbesserungsvorschläge


## 9. Best Practices

- **Baustein-Lieferung:** Neue Shader-Bausteine werden komplett geliefert; jede Node im 7-Punkte-Format erklärt; ein gemeinsamer Testabschnitt pro Baustein;
- **Verifikation vor Fortschritt:** Jeder Baustein wird direkt nach Aufbau per MCP verifiziert, bevor der nächste beginnt.
- **MCP-Disziplin:** Werte setzen und rücklesen in getrennten Call
- **Datensicherheit:** Vor `transform_apply` oder anderen destruktiven Operationen immer vom Backup arbeiten.

## 10. Nächste Schritte


## 11. Abhängigkeiten zu anderen Dokumenten

- `00_WORKSPACE_RULES.md` – dauerhafte Workspace-Regeln
- `02_Asset_Registry.md` – Szene, Materialien, Referenzmaterial
- `03_Shader_Architecture.md` – Shader-Ist und -Konzept
- `04_Progress_Log.md` – Sessionverlauf
- `05_Decision_Log.md` – Entscheidungen (D-Nummern)
- `06_Known_Issues.md` – offene Probleme (KI-Nummern)
- `07_Reference_Analysis.md` – gemessene Referenz-Erkenntnisse (Licht, Shading, Kamera, Cluster)


