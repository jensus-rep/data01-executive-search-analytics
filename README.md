# DATA01 Executive Search Analytics Assignment

Dieses Repository enthält die Arbeitsgrundlage für das Assignment im Modul Data Analytics. Ziel des Projekts ist die Entwicklung eines datengetriebenen Akquise Ansatzes im Executive Search auf Basis historischer Sales Daten auf Debitor Ebene.

## Projektziel

Untersucht wird, wie bestehende Kundenbeziehungen im Executive Search auf Basis historischer Sales Daten aggregiert, strukturell beschrieben und segmentiert werden können. Aufbauend auf diesen internen Mustern wird ein konzeptioneller Lookalike Ansatz für externe Zielunternehmen entwickelt.

Das Vorhaben ist als Proof of Concept angelegt. Ziel ist kein fertiges Produktivsystem, sondern ein methodisch sauberer und nachvollziehbarer Analyseprozess, der zugleich die Anforderungen der Prüfungsleistung erfüllt.

## Repository Struktur

`notebooks/`  
Enthält die zentralen Analyse Notebooks der Pipeline.

`data/raw/`  
Enthält lokale Rohdaten. Dieser Ordner wird nicht versioniert.

`data/processed/`  
Enthält lokal erzeugte Zwischenstände und Analyse Artefakte. Dieser Ordner wird nicht versioniert.

`docs/notes/`  
Enthält methodische Notizen, Projektdokumentation und vorbereitende Ausarbeitungen.

`src/`  
Ist für spätere Hilfsfunktionen oder optionale Auslagerungen vorgesehen.

## Analytische Pipeline

Die Notebook Pipeline ist in fünf aufeinander aufbauende Schritte gegliedert.

### 01 Import and Debitor Matrix

Datei  
`notebooks/01_import_and_debitor_matrix.ipynb`

Zweck  
Einlesen der vorbereiteten Rohdaten, grundlegende Struktur und Plausibilitätsprüfungen, Aggregation auf Debitor Ebene und Aufbau einer ersten Debitor Feature Matrix.

Typische Outputs  
Bereinigte und aggregierte Debitor Basis für die weitere Analyse.

### 02 EDA and Cleaning

Datei  
`notebooks/02_eda_and_cleaning.ipynb`

Zweck  
Explorative Analyse der Debitor Matrix, Prüfung von Fehlwerten, Auffälligkeiten und Verteilungen sowie fachlich begründetes Cleaning der Analysebasis.

Typische Outputs  
Bereinigte Debitor Arbeitsbasis für das Feature Engineering.

### 03 Feature Engineering and Baseline Clustering

Datei  
`notebooks/03_feature_engineering_and_baseline_clustering.ipynb`

Zweck  
Ableitung zusätzlicher Merkmale, Konsolidierung der Merkmalsbasis, Aufbau der Baseline Matrix und erste Clustering Läufe.

Typische Outputs  
Finale Debitor Feature Matrix, Baseline Feature Set, standardisierte Modellbasis, erste Cluster Ergebnisse.

### 04 Validation and Robustness

Datei  
`notebooks/04_validation_and_robustness.ipynb`

Zweck  
Bewertung der Clusterqualität über mehrere Metriken sowie Prüfung alternativer Feature Sets zur Robustheitsanalyse.

Typische Outputs  
Vergleich der Varianten, Validierungsmetriken, Einordnung metrischer und fachlicher Unterschiede.

### 05 Interpretation and Lookalike PoC

Datei  
`notebooks/05_interpretation_and_lookalike_poc.ipynb`

Zweck  
Inhaltliche Segmentbewertung, Auswahl der fachlichen Hauptlösung, Ableitung interpretierbarer Kundentypen sowie konzeptioneller externer Lookalike Transfer.

Typische Outputs  
Beschriebene Kundensegmente, priorisierte Zielsegmente, heuristischer Lookalike PoC, methodische Reflexion der Grenzen.

## Reihenfolge der Ausführung

Die Notebooks sind in numerischer Reihenfolge auszuführen.

1. `01_import_and_debitor_matrix.ipynb`
2. `02_eda_and_cleaning.ipynb`
3. `03_feature_engineering_and_baseline_clustering.ipynb`
4. `04_validation_and_robustness.ipynb`
5. `05_interpretation_and_lookalike_poc.ipynb`

Da einzelne Notebooks auf lokal erzeugten Zwischenständen aufbauen, sollte die Pipeline bei einem frischen Lauf in genau dieser Reihenfolge ausgeführt werden.

## Daten und Reproduzierbarkeit

Die Analyse arbeitet mit internen historischen Sales Daten. Aus Gründen der Vertraulichkeit werden Rohdaten und lokal erzeugte Zwischenstände nicht versioniert.

Für eine reproduzierbare Ausführung müssen daher lokal verfügbar sein:

- die vorbereitete Input Datei im erwarteten Rohdatenpfad
- die erforderlichen Python Pakete in der lokalen Umgebung
- Schreibrechte für lokale Zwischenstände in `data/processed/`

Die inhaltliche Logik der Analyse ist reproduzierbar dokumentiert. Eine vollständige technische Reproduzierbarkeit setzt jedoch voraus, dass die lokale Datenbasis und die verwendete Umgebung konsistent bereitgestellt werden.

## Hinweise zur Einordnung

Die Analyse ist als datengetriebener Proof of Concept zu verstehen. Die interne Segmentierung dient dem strukturellen Verständnis historischer Kundenbeziehungen auf Debitor Ebene. Der externe Lookalike Teil ist ein explorativer Transfer interner Muster in externe Proxy Dimensionen und kein validiertes produktives Scoring System.

## Status

Das Repository befindet sich im Arbeitsstand der Assignment Entwicklung. Die Notebook Pipeline ist fachlich weitgehend aufgebaut und wird aktuell hinsichtlich Dokumentation, Reproduzierbarkeit und schriftlicher Ausarbeitung nachgeschärft.