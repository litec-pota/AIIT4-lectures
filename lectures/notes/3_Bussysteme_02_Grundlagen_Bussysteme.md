---
title: Skriptum Bussysteme
subtitle: Teil 2 Grundlagen Bussysteme
author: 
    - DI(FH) Andreas Pötscher, HTL Litec
documentclass: scrartcl
geometry: 
- a4paper
- margin=25mm 
---

\vspace{12mm}

*Copyright- und Lizenz-Vermerk:
Das vorliegende Werk kann unter den Bedingungen der Creative Commons License CC-BY-SA 3.0, siehe
http://creativecommons.org/licenses/by-sa/3.0/deed.de, frei vervielfältigt, verbreitet und verändert werden. Eine kurze, allgemein verständliche Erklärung dieser Lizenz kann unter http://creativecommons.org/licenses/by-sa/3.0/deed.de gefunden werden. Falls Sie Änderungen durchführen, dokumentieren Sie diese im folgenden Änderungsverzeichnis:*


Datum            | Beschreibung der durchgeführten Änderung                          | Autor
---------------- | ------------------------------------------------------------------|---------------------------------------------------
09.04.2025       | V1.0 ...1.Version Basierend auf FI1 bis FI3 von Gebhard Klinkan   | Andreas Pötscher, HTL Linz–Paul-Hahn-Straße (LiTec)


# Einführung

% Allgemeine Einführung / Bustoplogien / Fehlererkennung (Paritätsbit / Prüfsumme) / Buszugriffssteuerung

Ein Bus ist ein System zur Datenübertragung zwischen mehreren Teilnehmern über ein gemeinsames Übertragungsmedium. Die an einen Bus angeschlossenen Komponenten werden auch als Busteilnehmer oder Busknoten bezeichnet.

Ein Feldbussystem ist ein Datennetzwerk auf industrieller Ebene. An dieses Netzwerk können E/A-Module (Ein-/Ausgabe-Module), Sensoren und Aktoren mit einem Steuerungsrechner verbunden werden. Feldbussysteme sind leistungsfähiger, flexibler und kostengünstiger als herkömmliche Verdrahtungslösungen und haben diese in der Praxis weitgehend ersetzt.


# Vorteile von Bussystemen

- Projektierungs- und Installationskosten
günstige Kabel, einfache Pläne, geringer Platzbedarf, schnelle und fehlersichere Verdrahtung
- einfache Erweiterbarkeit
zusätzliche Busteilnehmer über einfache Busverlängerung und Konfiguration in der Software
- Parameter- und Diagnosefunktionen
Parametrierung und laufende Überwachung aller Busteilnehmer im Betrieb

# Merkmale und Anwendungsbereiche

Aktuell ist eine Vielzahl an unterschiedlichen Bussystemen erhältlich. Die Systeme unterscheiden sich je nach Einsatzgebiet in der Netzarchitektur, im Datendurchsatz, in der Echtzeitfähigkeit und der Übertragungs¬technik.

Bussysteme sind oftmals für einen bestimmten Anwendungsbereich konzipiert, was aber nicht bedeutet, dass jeder Bustyp nur für eine bestimmte Anwendung verwendbar ist. Beispiel für verschiedene Anwendungen von Bussysteme sind:

**CAN-Bus (Controller Area Network)**

- Technik: Serielles Bussystem mit Prioritätssteuerung und Fehlersicherheit.
- Anwendung: Kfz-Elektronik (z. B. Motorsteuerung, Airbags, ABS).

**Profibus (Process Field Bus)**

- Technik: Industrielles Feldbussystem, unterstützt Master-Slave-Kommunikation.
- Anwendung: Automatisierungstechnik, SPS-Systeme in der Fertigung.

**Modbus:**

- Technik: Einfaches Master-Slave-Protokoll über serielle Schnittstellen oder TCP/IP.
- Anwendung: Gebäudeautomation, industrielle Kommunikation.

**I²C (Inter-Integrated Circuit)**

- Technik: Zweidraht-Bus für kurze Distanzen zwischen ICs, Master-Slave-Architektur.
- Anwendung: Kommunikation zwischen Mikrocontrollern und Sensoren.

**USB (Universal Serial Bus)**

- Technik: Serielles Plug-and-Play-Bussystem mit Hot-Plug-Funktion.
- Anwendung: PC-Peripheriegeräte wie Tastatur, Maus, Speichergeräte.



# Automatisierungspyramide




