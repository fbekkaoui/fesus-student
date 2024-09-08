
# FESuS

Dieses Projekt kann als Ausgangspunkt verwendet werden, um eine eigene Vaadin-Anwendung mit Spring Boot zu erstellen. Es enthält alle notwendigen Konfigurationen und einige Platzhalter-Dateien, um den Einstieg zu erleichtern.

## Anwendung ausführen

Das Projekt ist ein standardmäßiges Maven-Projekt. Um es über die Kommandozeile zu starten, geben Sie `mvnw` (Windows) oder `./mvnw` (Mac & Linux) ein und öffnen Sie dann http://localhost:8080 in Ihrem Browser.

Sie können das Projekt auch in Ihre bevorzugte IDE importieren, wie Sie es mit jedem Maven-Projekt tun würden. Weitere Informationen finden Sie in der [Anleitung zum Importieren von Vaadin-Projekten in verschiedene IDEs](https://vaadin.com/docs/latest/guide/step-by-step/importing) (Eclipse, IntelliJ IDEA, NetBeans und VS Code).

## Deployment in die Produktion

Um einen Produktions-Build zu erstellen, führen Sie `mvnw clean package -Pproduction` (Windows) oder `./mvnw clean package -Pproduction` (Mac & Linux) aus. Dies erstellt eine JAR-Datei mit allen Abhängigkeiten und Frontend-Ressourcen, die bereit für den Einsatz ist. Die Datei befindet sich nach Abschluss des Builds im `target`-Ordner.

Sobald die JAR-Datei erstellt ist, können Sie sie mit dem Befehl `java -jar target/fesus-1.0-SNAPSHOT.jar` ausführen.

## Projektstruktur

- `MainLayout.java` im Ordner `src/main/java` enthält das Navigations-Setup (d.h. die Seiten-/Top-Leiste und das Hauptmenü). Dieses Setup verwendet das [App Layout](https://vaadin.com/docs/components/app-layout).
- Das Paket `views` im Ordner `src/main/java` enthält die serverseitigen Java-Ansichten Ihrer Anwendung.
- Der Ordner `views` im Verzeichnis `frontend/` enthält die clientseitigen JavaScript-Ansichten Ihrer Anwendung.
- Der Ordner `themes` im Verzeichnis `frontend/` enthält die benutzerdefinierten CSS-Stile.

## Nützliche Links

- Lesen Sie die Dokumentation unter [vaadin.com/docs](https://vaadin.com/docs).
- Folgen Sie dem Tutorial unter [vaadin.com/docs/latest/tutorial/overview](https://vaadin.com/docs/latest/tutorial/overview).
- Erstellen Sie neue Projekte unter [start.vaadin.com](https://start.vaadin.com/).
- Suchen Sie nach UI-Komponenten und Anwendungsbeispielen unter [vaadin.com/docs/latest/components](https://vaadin.com/docs/latest/components).
- Sehen Sie sich Anwendungsbeispiele an unter [vaadin.com](https://vaadin.com/).

## Deployment mit Docker

Um das Projekt mit Docker bereitzustellen, können Sie die im Projekt enthaltene `Dockerfile` verwenden, um ein Docker-Image zu erstellen und die Anwendung in einem Docker-Container auszuführen. Führen Sie die folgenden Schritte aus:

```
mvn clean package -Pproduction
docker build . -t fesus:latest
```

Führen Sie den Docker-Container aus:

```
docker run -p 8080:8080 fesus:latest
```
