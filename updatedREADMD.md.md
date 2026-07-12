# LAVU OÖ - Etiketten-Druckstudio v9 🏷️🖨️

Ein schlankes, datenschutzfreundliches und offline-fähiges Web-Tool (PWA) zur schnellen Generierung und zum passgenauen Druck von Abfall- und Materialetiketten auf **HERMA A4-Etikettenbögen** mit verschiedenen Formaten. Optimiert für den Einsatz in Altstoffsammelzentren (ASZ) in Oberösterreich.

## ✨ Features

*   **Flexible Etikettenformate:** Unterstützt zahlreiche HERMA-Bögen (z.B. 4473, 4273, 4428, 4465, etc.) – wählbar in den Druckoptionen.
*   **Interaktiver A4-Druckbogen:** Vorschau anklicken, um Etiketten flexibel hinzuzufügen oder zu entfernen (schont angefangene Etikettenbögen!).
*   **Zentrale Datenpflege:** Lädt das Artikelsortiment standardmäßig dynamisch als JSON direkt aus diesem GitHub-Repository.
*   **Externe Standortdaten:** Die Liste der ASZ-Standorte wird aus einer zentralen `locations.json` geladen und kann zentral gepflegt werden.
*   **Offline-First (PWA):** Vollständig als Progressive Web App installierbar. Läuft dank Service Worker und `localStorage`-Caching auch bei Netzwerkunterbrechungen stabil.
*   **Flexibler Workspace:** Integrierte CRUD-Funktionen zum Bearbeiten, Hinzufügen und Löschen von Artikeln im lokalen Cache inklusive JSON-Export.
*   **Mehrsprachigkeit:** Unterstützung für Deutsch und Englisch (umschaltbar).

## 📂 Repository-Struktur
