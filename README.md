# Projekt

### Diogo Da Costa

### 18.09.26

## Projektbeschreibung

In diesem Projekt wird eine Anwendung erstellt, die lokal auf dem Computer oder mit Docker gestartet werden kann.

Für die Verwaltung des Projekts wird **Git** verwendet. Mit **Docker** kann die Anwendung in einem Container ausgeführt werden. Mit **Docker Compose** können die benötigten Container einfacher gestartet und gestoppt werden.

Diese README zeigt die wichtigsten Schritte, damit das Projekt auf einem anderen Computer eingerichtet und gestartet werden kann.

---

## Voraussetzungen

Damit das Projekt verwendet werden kann, sollten folgende Programme installiert sein:

- Git
- Docker Desktop
- Visual Studio Code
- Node.js
- npm

Ob die Programme installiert sind, kann im Terminal überprüft werden:

```bash
git --version
docker --version
docker compose version
node --version
npm --version
```

Wenn bei den Befehlen eine Versionsnummer angezeigt wird, ist das jeweilige Programm installiert.

---

## Repository klonen

Als Erstes muss das Repository auf den eigenen Computer heruntergeladen werden.

Dazu wird folgender Befehl verwendet:

```bash
git clone <REPOSITORY-URL>
```

Bei `<REPOSITORY-URL>` muss die URL des eigenen Git-Repositories eingefügt werden.

Beispiel:

```bash
git clone https://gitlab.com/benutzer/projekt.git
```

Danach wechselt man in den Projektordner:

```bash
cd projekt
```

Nun befindet man sich im richtigen Verzeichnis und kann mit der Installation beginnen.

---

## Pakete installieren

Die Anwendung benötigt verschiedene Pakete und Abhängigkeiten.

Diese können mit folgendem Befehl installiert werden:

```bash
npm install
```

npm liest dabei die Datei `package.json` und installiert automatisch die Pakete, die für das Projekt benötigt werden.

Nach der Installation befindet sich normalerweise ein Ordner namens `node_modules` im Projekt.

---

## Anwendung lokal starten

Die Anwendung kann zuerst lokal gestartet werden, um zu prüfen, ob alles funktioniert.

Je nach Projekt wird dafür folgender Befehl verwendet:

```bash
npm start
```

Oder im Entwicklungsmodus:

```bash
npm run dev
```

Wenn die Anwendung erfolgreich gestartet wurde, kann sie über den Browser geöffnet werden.

Zum Beispiel:

```text
http://localhost:3000
```

Der verwendete Port kann je nach Projekt unterschiedlich sein.

---

## Docker-Image erstellen

Damit die Anwendung mit Docker gestartet werden kann, muss zuerst ein Docker-Image erstellt werden.

Dafür wird im Projektordner folgender Befehl ausgeführt:

```bash
docker build -t meine-app .
```

Dabei wird das vorhandene `Dockerfile` verwendet.

`meine-app` ist der Name des Docker-Images und kann auch durch einen eigenen Namen ersetzt werden.

Mit folgendem Befehl können die vorhandenen Docker-Images angezeigt werden:

```bash
docker images
```

Wenn das Image in der Liste erscheint, wurde es erfolgreich erstellt.

---

## Anwendung mit Docker starten

Nach dem Erstellen des Images kann daraus ein Container gestartet werden.

```bash
docker run -d -p 3000:3000 --name meine-app-container meine-app
```

Kurze Erklärung:

- `-d` startet den Container im Hintergrund
- `-p 3000:3000` verbindet den Port des Computers mit dem Port des Containers
- `--name` gibt dem Container einen Namen
- `meine-app` ist das zuvor erstellte Docker-Image

Mit folgendem Befehl kann geprüft werden, ob der Container läuft:

```bash
docker ps
```

Wenn der Container dort angezeigt wird, wurde er erfolgreich gestartet.

---

## Anwendung mit Docker Compose starten

Wenn im Projekt eine Datei wie `compose.yml` oder `docker-compose.yml` vorhanden ist, kann die Anwendung auch mit Docker Compose gestartet werden.

```bash
docker compose up -d
```

Docker Compose liest die Konfiguration aus der Compose-Datei und startet die dort definierten Container.

Mit folgendem Befehl kann der Status überprüft werden:

```bash
docker compose ps
```

Falls Fehler auftreten, können die Logs angezeigt werden:

```bash
docker compose logs
```

Damit sieht man die Ausgaben der Container und kann mögliche Probleme einfacher finden.

---

## Anwendung stoppen

### Docker-Container stoppen

Wenn die Anwendung direkt mit Docker gestartet wurde, kann der Container so gestoppt werden:

```bash
docker stop meine-app-container
```

Wenn der Container nicht mehr benötigt wird, kann er danach entfernt werden:

```bash
docker rm meine-app-container
```

---

### Docker Compose stoppen

Wenn die Anwendung mit Docker Compose gestartet wurde, kann sie mit folgendem Befehl gestoppt werden:

```bash
docker compose down
```

Damit werden die gestarteten Container gestoppt und entfernt.

---

## Wichtige Befehle

Hier sind die wichtigsten Befehle nochmals kurz zusammengefasst:

```bash
# Repository klonen
git clone <REPOSITORY-URL>

# In den Projektordner wechseln
cd projekt

# Pakete installieren
npm install

# Anwendung lokal starten
npm start

# Docker-Image erstellen
docker build -t meine-app .

# Docker-Container starten
docker run -d -p 3000:3000 --name meine-app-container meine-app

# Docker Compose starten
docker compose up -d

# Docker Compose stoppen
docker compose down
```

---

**Name:** Vorname Nachname  
**Projekt:** Docker-Projekt
