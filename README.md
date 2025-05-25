# 🛠️ DevOps 02 – Build Tools

## 👥 Zusammenarbeit

### 📄 Person und Repository

|                          |                                                                                      |
|--------------------------|--------------------------------------------------------------------------------------|
| Bearbeiter               | Alessio Pugliese                                                                    |
| Repo URL Gradle          | [DevOps-02-Build](https://github.com/pugliale/DevOps-02-Build.git)                  |                                |

---

## 📖 Theoretischer Hintergrund

### 🧰 Was sind Build Tools?

Build-Tools automatisieren die Erstellung von ausführbaren Anwendungen aus dem Quellcode. Anstatt manuelle Kommandos wie Kompilierung, Archivierung oder Deployment auszuführen, übernimmt ein Build-Tool diese Aufgaben automatisiert und reproduzierbar. Typische Aufgaben eines Build-Tools sind:

- Kompilieren von Quellcode (z. B. Java → Bytecode)
- Verpacken der Anwendung (z. B. als `.jar`)
- Verwaltung externer Bibliotheken (Dependencies)
- Durchführung von Tests und Qualitätssicherung
- Bereitstellung für Deployment

Build-Tools tragen entscheidend zur **Effizienz und Konsistenz** im DevOps-Prozess bei.

---

### ☕ Gradle – Build Tool für Java

Gradle ist ein modernes Build-Tool für Java-Projekte. Es basiert auf dem Prinzip „Convention over Configuration“ und verwendet eine deklarative Syntax mit **Groovy** oder **Kotlin DSL** anstelle von XML (wie bei Maven). Vorteile:

- Schnelle Builds durch den Gradle Daemon
- Flexibel durch programmierbare Build-Logik
- Unterstützt Dependency Management über Maven Central

---

### 🌐 NPM – Node Package Manager

NPM ist das Standard-Tool für die Verwaltung von Abhängigkeiten in **JavaScript/Node.js**-Projekten. Es erlaubt das einfache Einbinden von Bibliotheken (z. B. Chart.js, Anime.js, Vue.js), das Starten von Skripten und die Definition von Projekt-Metadaten über die `package.json`.

---

## 💻 Verwendete Systeme und Tools

- **Gradle** – Build-Tool für Java
- **Maven Central** – Repository für Java-Libraries
- **Java (JDK)** – Ausführung der Applikationen
- **Visual Studio Code** – Hauptentwicklungsumgebung inkl. Terminal & Erweiterungen
- **NPM** – Build-Tool und Paketmanager für JavaScript
- **HTML / JavaScript** – für Frontend-Demonstrationen (Chart.js, Anime.js, Vue.js)
- **Git & GitHub** – zur Versionierung und Dokumentation

---

## 🔨 Praktische Umsetzung

### ⚙️ Gradle-Projekt

#### 📁 Projekt initialisieren

Im ersten Schritt wurde ein neues Repository auf GitHub erstellt und anschliessend lokal geklont. In Visual Studio Code wurde der Befehl `gradle init` ausgeführt, um ein neues Gradle-Projekt zu generieren. Dabei wurden die Optionen „Application“, „Java“ und „Groovy“ ausgewählt. Dies erzeugte die nötige Projektstruktur inklusive `build.gradle` und dem Ordner `src`.

<img src="Images/Bild1.png" alt="Gradle Init" width="600">

#### ▶️ Projekt testen & Umgebung einrichten

Nach der Initialisierung wurde das Projekt mit dem Befehl `gradle run` getestet. Dabei wurde festgestellt, dass Visual Studio Code die Projektstruktur (insbesondere Java und Gradle) nicht direkt erkannt hat. Durch das Schliessen und erneute Öffnen des Projektordners wurde die Gradle-Integration korrekt initialisiert – u.a. erkennbar am „Gradle-Elefant“-Symbol und dem erkannten Java-Projekt in der Seitenleiste.

<img src="Images/Bild2.png" alt="Gradle Run" width="600">
<img src="Images/Bild3.png" alt="Projektstruktur" width="600">

#### 📝 build.gradle anpassen

Im nächsten Schritt wurde die Datei `build.gradle` geöffnet und manuell editiert. Die Sektionen `plugins`, `repositories`, `dependencies` und `application` wurden ergänzt bzw. angepasst, um das Projekt auf den späteren Code und die gewünschten Bibliotheken vorzubereiten.

<img src="Images/Bild5.png" alt="build.gradle geöffnet" width="600">

#### 📦 Dependency hinzufügen: java-ascii-render

Über [search.maven.org](https://search.maven.org) wurde die Bibliothek `java-ascii-render` gesucht. Die Dependency wurde gemäss der Maven-Vorgaben in `build.gradle` eingefügt. Diese Bibliothek erlaubt das Darstellen von ASCII-Textausgaben in der Konsole.

<img src="Images/Bild6.png" alt="Dependency hinzugefügt" width="600">

In der Datei `App.java` wurde anschliessend ein Beispielcode eingebunden, um eine ASCII-Ausgabe zu erzeugen. Der Code wurde erfolgreich mit `gradle run` ausgeführt.

<img src="Images/Bild7.png" alt="Java-Ausgabe" width="600">

#### 📦 Dependency hinzufügen: pdfbox

Zusätzlich wurde die Bibliothek `pdfbox` von Apache eingebunden, um eine PDF-Datei mit Textinhalt zu erzeugen. Die Dependency wurde über Maven eingebunden und in `App.java` entsprechend verwendet. Auch hier wurde nach dem Speichern des Codes `gradle run` ausgeführt.

<img src="Images/Bild8.png" alt="PDFBox hinzugefügt" width="600">
<img src="Images/Bild9.png" alt="PDF-Ausgabe" width="600">

Am Ende wurde erfolgreich eine PDF-Datei generiert und lokal gespeichert. Damit war der Build-Prozess für zwei unterschiedliche Use-Cases (Konsole & PDF) abgeschlossen.

<img src="Images/Bild10.png" alt="PDF erfolgreich erstellt" width="600">

---

### 🌐 NPM-Projekt

#### 📁 Projekt initialisieren

Ein neues Verzeichnis `SW4NPM` wurde lokal erstellt und mit Visual Studio Code geöffnet. Anschliessend wurde über das Terminal der Befehl `npm init` ausgeführt, um die Datei `package.json` zu erzeugen. Dabei wurden die Standardwerte übernommen.

<img src="Images/Bild1_NPM.png" alt="npm init" width="600">

#### 📊 Beispiel: Chart.js

Für das erste Beispiel wurde eine HTML-Datei `chart.html` erstellt. In dieser wurde Chart.js als externe Bibliothek eingebunden. Die Datei enthielt einen einfachen Balkendiagramm-Code, der direkt im Browser geöffnet wurde.

<img src="Images/Bild2_NPM.png" alt="chart.html" width="600">
<img src="Images/Bild3_NPM.png" alt="Chart Darstellung" width="600">

Anschliessend wurde Chart.js lokal via `npm install chart.js` installiert. Die Datei wurde angepasst, um die Bibliothek aus dem `node_modules`-Ordner zu referenzieren.

<img src="Images/Bild4_NPM.png" alt="npm install chart.js" width="600">
<img src="Images/Bild5_NPM.png" alt="Lokale Bibliothek" width="600">
<img src="Images/Bild6_NPM.png" alt="Erfolgreiche Anzeige" width="600">

#### 🎞️ Beispiel: anime.js

Anschliessend wurde ein zweites Beispiel mit der Bibliothek `anime.js` umgesetzt. Die Bibliothek wurde via `npm install animejs` installiert und ein einfaches DOM-Element animiert. Das Beispiel wurde ebenfalls lokal im Browser getestet.

<img src="Images/Bild7_NPM.png" alt="anime.js" width="600">

#### ⚛️ Beispiel: Vue.js

Als dritte Frontend-Bibliothek wurde Vue.js eingebunden. Es wurde ein Beispiel aus dem Internet verwendet, bei dem eine Liste von Elementen angezeigt und erweitert werden kann. Vue wurde lokal eingebunden und in einer eigenen HTML-Datei getestet.

<img src="Images/Bild8_NPM.png" alt="Vue Beispiel 1" width="600">
<img src="Images/Bild9_NPM.png" alt="Vue Beispiel 2" width="600">
<img src="Images/Bild10_NPM.png" alt="Vue Beispiel 3" width="600">


## ✅ Erkenntnisse und Reflexion

### 🔍 Was habe ich gelernt?

- Der Einsatz von **Build-Tools** reduziert manuelle Arbeit und minimiert Fehlerquellen im Entwicklungsprozess.
- **Gradle** bietet ein flexibles und effizientes Framework für Java-Projekte mit klaren Vorteilen gegenüber älteren Tools wie Ant oder Maven.
- Mit **NPM** lassen sich Frontend-Bibliotheken einfach integrieren und verwalten – insbesondere bei reaktiven Frameworks wie Vue.js ist dies essenziell.
- Das Zusammenspiel von **Code**, **Build-Konfiguration**, **Dependency Management** und **Ausführung** ist zentraler Bestandteil moderner Softwareentwicklung.

### 🧠 Fazit

Diese Lektion hat mein Verständnis für die Bedeutung automatisierter Build-Prozesse stark erweitert. Besonders der Unterschied zwischen Java- und JavaScript-Projekten sowie deren jeweilige Toolchains (Gradle vs. NPM) war sehr lehrreich.

> 💬 *„Build once, run anywhere – aber automatisiert!“*

---

📅 *Frühjahrssemester 2025 – ZHAW School of Management and Law*
