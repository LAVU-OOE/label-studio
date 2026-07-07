# LAVU OÖ - Etiketten-Druckstudio v8 🏷️🖨️

Ein schlankes, datenschutzfreundliches und offline-fähiges Web-Tool (PWA) zur schnellen Generierung und zum passgenauen Druck von Abfall- und Materialetiketten auf **HERMA 4473 Bogen** (3 × 7 Etiketten pro A4-Seite, 70 × 41 mm). 

Optimiert für den Einsatz in Altstoffsammelzentren (ASZ) in Oberösterreich, bietet dieses Tool ein interaktives Layout-Management, bei dem benutzte oder freie Druckpositionen direkt per Klick zugewiesen werden können.

## ✨ Features

* **Perfekte Passform:** Exakt abgestimmt auf das Format **HERMA 4473** (70 × 41 mm).
* **Interaktiver A4-Druckbogen:** Vorschau anklicken, um Etiketten flexibel hinzuzufügen oder zu entfernen (schont angefangene Etikettenbögen!).
* **Zentrale Datenpflege:** Lädt das Artikelsortiment standardmäßig dynamisch als JSON direkt aus diesem GitHub-Repository.
* **Offline-First (PWA):** Vollständig als Progressive Web App installierbar. Läuft dank Service Worker und `localStorage`-Caching auch bei Netzwerkunterbrechungen stabil.
* **Flexibler Workspace:** Integrierte CRUD-Funktionen zum Bearbeiten, Hinzufügen und Löschen von Artikeln im lokalen Cache inklusive JSON-Export.
* **Standort-Vorauswahl:** Schnelle Anpassung der Kopfzeile für oberösterreichische Bezirke und ASZ-Standorte (z.B. *106 - ASZ Asten*).

---

## 🛠️ Repository-Struktur

Für die vollständige Funktionalität der PWA sollte das Repository mindestens folgende Dateien im Root-Verzeichnis enthalten:

```text
├── index.html        # Die Hauptanwendung (UI, Logik & Druck-CSS)
├── sortiment.json    # Die zentrale Artikeldatenbank (GitHub-Raw-Quelle)
├── manifest.json     # PWA-Konfiguration für die App-Installation
├── sw.js             # Service Worker für den Offline-Betrieb
├── favicon.svg       # App-Icon im Vektorformat
└── logo.png          # Sender-Logo für die App-Kopfzeile
