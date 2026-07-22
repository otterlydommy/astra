# WORKSPACE_RULES.md

# Nova Workspace Rules

Diese Datei enthält alle langfristig gültigen Regeln des Astra-Workspaces.

---

# Projekt

Aktives Projekt:


Dokumentationsname:


---

# Blender

* Blender 5.2 LTS
* BlenderMCP wird verwendet.
* MCP bindet an den Blender-Prozess, nicht an einzelne Dateien.
* Hardware: NVIDIA GeForce RTX 2070 (8 GB VRAM)

---

# Arbeitsdateien

---

# MCP

* Claude arbeitet standardmäßig ausschließlich lesend (analysieren, messen, verifizieren, rendern zur Prüfung).
* Änderungen jeder Art über MCP nur nach expliziter Freigabe im Chat – nur die konkret freigegebenen Änderungen.
* Werte setzen und rücklesen in getrennten MCP-Calls.
* Messen statt raten; ohne Live-Verbindung explizit „nicht live geprüft" sagen.

---

# Shader-Regeln

* Verbindliche Design-Pfeiler: siehe `01_Project_Vision.md` §5 (dort gepflegt, hier nicht dupliziert).

---

# Designprinzipien

* reproduzierbar
* modular
* wartbar
* nachvollziehbar
* dokumentiert
* möglichst einfach
* Debugbarkeit berücksichtigen

---

# Projektrichtlinien

* bestehende Systeme erweitern statt ersetzen
* keine Parallelstrukturen
* keine Quick-Fixes
* langfristige Wartbarkeit vor kurzfristiger Geschwindigkeit
* Eigenentwicklung vor Kopieren fremder Lösungen
* Änderungen müssen nachvollziehbar dokumentiert werden

---

# Dokumentation

Die Dokumentation ist Bestandteil der Entwicklung und kein nachträglicher Schritt.

---

# Verbindliche Dokumente

Alle Detailregeln befinden sich in `.claude`.


Diese Dokumente bilden gemeinsam das Projektgedächtnis und haben Vorrang vor Chatverläufen oder Erinnerungen.
