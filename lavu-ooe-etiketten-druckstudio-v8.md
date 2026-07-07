# LAVU OÖ - Etiketten-Druckstudio v8 (HERMA 4473)
## Anwendungsdokumentation und Datenübersicht


Dieses Dokument enthält eine strukturierte Markdown-Zusammenfassung der Web-Anwendung **LAVU OÖ - Etiketten-Druckstudio v8**. Die App dient zum Drucken von normierten Abfallentsorgungs-Etiketten basierend auf dem Vorlagenformat **HERMA 4473**.

---

## 1. Technische Spezifikationen

- **Layout-Format**: HERMA 4473 (A4-Bogen mit insgesamt 21 Etiketten)
- **Raster-Anordnung**: 3 Spalten × 7 Zeilen (Raster-Layout)
- **Etikettengröße**: Jeweils ca. 70 × 41 mm
- **Druckeigenschaften**: 
  - Randloser A4-Druck (`@page { size: A4; margin: 0; }`)
  - Ausblendung von Hilfslinien und UI-Elementen im Druckmodus (`@media print`)
  - Flexibler Druck ab einer bestimmbaren Startposition (Ermöglicht Restverwertung angebrochener Bögen)
- **Zustandsspeicherung**: Lokale Speicherung der Konfiguration über den Browser (`localStorage` Key: `lavu_studio_defaults_v8`)
- **PWA-Unterstützung**: Service Worker Integration (`sw.js`) für Offline-Funktionalität

---

## 2. Verfügbares Abfallsortiment (Artikelstammdaten)

Das System verfügt über 15 vordefinierte Abfallarten im Sortiment, welche direkt geladen werden können:

| Art.-Nr. | Abfallbezeichnung (unten) | Zusatztext (Mitte) | Bestimmungsort / Behältertyp |
| :---: | :--- | :--- | :--- |
| **4040** | Elektro-Kleingeräte (ohne Akku) | QR-Box | Sammelbehälter / Box |
| **4010** | Elektro-Großgeräte | Gitterbox | Sammelbehälter / Box |
| **4020** | Kühlgeräte | Großteil | Freifläche / Stellplatz |
| **4030** | Bildschirmgeräte | Gitterbox | Sammelbehälter / Box |
| **4015** | Nachtspeicheröfen | Spezial | Sonderabwicklung |
| **4050** | Gasentladungslampen | Karton | Verpackungsmedium |
| **3000** | Altpapier (Deinking-Qualität) | Container | Großbehälter |
| **2100** | Kartonagen (ARA-lizenziert) | Presse | Verdichtungsanlage |
| **3200** | Alteisen | Mulde | Großbehälter |
| **3210** | Nichteisen-Metalle | Box | Kleinsortierung |
| **3300** | Altholz | AII-Holz | Qualitätsklasse |
| **3400** | Speisefett/-öl (Haushalts-Öl) | Fass | Sammelemballage |
| **3500** | Altreifen | Stapel | Lagerungsform |
| **4300** | Altlacke & Werkstättenabfälle | Gefahrgut | Sonderabfall-Box |
| **4320** | Altöle | Tank | Flüssiglagerung |

---

## 3. Standortauswahl (ASZ Niederlassungen OÖ)

In den Einstellungen können die folgenden Altstoffsammelzentren (ASZ) in Oberösterreich als Kopfzeile ausgewählt werden:

### Bezirk Linz-Land
- 106 - ASZ Asten *(Standard)*
- ASZ Ansfelden
- ASZ Enns
- ASZ Hörsching
- ASZ Leonding
- ASZ Neuhofen
- ASZ Pasching
- ASZ St. Florian
- ASZ Traun
- ASZ Wilhering

### Linz Stadt
- ASZ Linz-Nebingerstraße
- ASZ Linz-Mostnnystraße
- ASZ Linz-Wiener Straße
- ASZ Linz-Dornach

---

## 4. Funktions- und Benutzeroberflächenstruktur

Die Anwendung ist als Single-Page-Application (SPA) mit modernem Dashboard aufgebaut:

1. **Dashboard (Hauptseite)**:
   - **Live-Vorschau (Sidebar)**: Skalierte Miniaturansicht (Faktor 0.20) des gesamten A4-Druckbogens zur direkten optischen Kontrolle. Klick öffnet die Großansicht.
   - **Schnellauswahl**: Dropdown-Menü zur direkten Übernahme von Artikeln aus dem vordefinierten Sortiment.
   - **Aktuelle Konfiguration**: Übersicht der ausgewählten Werte (Bezeichnung, Artikelnummer, Zusatztext, geplante Druckmenge und Startposition).
   - **Aktionsbuttons**: Direkter Druckbefehl oder Aufruf des Einstellungsmenüs.

2. **Druck- & Standorteinstellungen (Modal)**:
   - Festlegung der ASZ-Dienststelle für die Kopfzeile.
   - Steuerung der Etikettenanzahl (Maximal 21 Stück pro Bogen).
   - Anpassung der Startposition (1 bis 21) zur Wiederverwendung benutzter Bögen.
   - **Modus-Umschalter**:
     - *Sortiment-Modus*: Verwendung der vordefinierten Abfallarten.
     - *Freie Eingabe*: Manuelle Eingabe einer individuellen Artikelnummer, eines Zusatztextes und einer individuellen Bezeichnung.
   - **Standard sichern**: Speichert den aktuellen Zustand persistent im `localStorage` ab.

3. **Vollbild-Druckvorschau (Modal)**:
   - Simulation des echten A4-Druckbogens im Originalmaßstab vor der Übergabe an das Drucksystem des Betriebssystems.

---

## 5. CSS Styling- & Designrichtlinien

- **Farbpalette**:
  - Primärfarbe (Header/Titel): `#1a4b60` (Dunkles Petrolblau)
  - Sekundärfarbe (Akzente): `#6cb4db` (Hellblau)
  - Erfolgsfarbe (Buttons/Status): `#27ae60` (Grün)
  - Hintergrund (UI): `#f4f7f9` (Hellgrau-Blau)
- **Typografie (Benutzeroberfläche)**: System-Font-Stack (`Segoe UI`, `-apple-system`, `Roboto`, `Arial`, etc.) für maximale Performance und geräteübergreifende Konsistenz.
- **Typografie (Etikettendruck)**: Fixierte, plattformübergreifend exakt skalierende Schriftarten (`Arial`, `Helvetica Neue`) mit Punkt-Größen (`pt`) zur Gewährleistung von absoluter Maßhaltigkeit beim physikalischen Druck.
