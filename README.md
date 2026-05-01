# Recherche-Cockpit Drucksache 21/5277

Untersuchungsplattform zur Auswertung der Förderpraxis der Bundeszentrale
für politische Bildung (bpb), basierend auf der Antwort der Bundesregierung
auf die Kleine Anfrage 21/04390 (Drucksache 21/5277, 7. April 2026).

## Zugriff

Die Datei `index.html` ist die gesamte Anwendung. Sie funktioniert
clientseitig im Browser ohne Server-Komponente. Wenn dieses Repository
über GitHub Pages bereitgestellt wird, ist das Cockpit unter der
veröffentlichten URL erreichbar (siehe Abschnitt *Aktivierung GitHub
Pages* weiter unten).

Die Inhalte sind AES-256-GCM-verschlüsselt; das Passwort wird per
PBKDF2-SHA256 mit 600.000 Iterationen aus der Eingabe abgeleitet. Ohne
korrektes Passwort sind weder die Recherchedaten noch die Tab-Struktur
einsehbar — die Datei zeigt in diesem Fall nur den Login-Schirm.

## Sicherheit

Dieses Repository ist als **privates** Repository auszuführen. Die
verschlüsselte `index.html` enthält die gesammelten Recherchedaten,
die zwar ohne Passwort nicht lesbar sind, aber dennoch nicht öffentlich
sichtbar gehalten werden sollten. Das Passwort wird ausschließlich
außerhalb des Repositories aufbewahrt — niemals committen.

Die `.gitignore`-Datei ist so konfiguriert, dass sie das Build-Skript
und alle passwortbezogenen Dateien automatisch aus jedem Commit
ausschließt; selbst ein versehentliches `git add .` kann diese Sperre
nicht umgehen.

## Aktivierung GitHub Pages

Nach dem ersten Hochladen der Dateien wird GitHub Pages in den
Repository-Einstellungen aktiviert: *Settings* → *Pages* →
*Source: Deploy from a branch* → *Branch: main, Folder: / (root)* →
*Save*. Nach wenigen Minuten ist das Cockpit unter der angezeigten
URL erreichbar.

Die Datei `.nojekyll` im Repository-Root signalisiert GitHub Pages,
dass die Inhalte unverändert bereitgestellt werden sollen — ohne die
sonst übliche Jekyll-Verarbeitung, die HTML-Dateien als Templates
behandeln würde.

## Aktualisierung

Wenn neue Daten oder Funktionen ins Cockpit aufgenommen werden, wird
die `index.html` außerhalb des Repositories neu gebaut und im
Repository einfach durch die neue Version ersetzt. Ein einfacher
Commit auf den main-Branch genügt; GitHub Pages aktualisiert die
veröffentlichte Version automatisch innerhalb weniger Minuten.

## Repository-Inhalt

| Datei | Zweck |
|-------|-------|
| `index.html` | Verschlüsseltes Cockpit (gesamte Anwendung) |
| `README.md` | Diese Datei |
| `.gitignore` | Schutz vor versehentlichem Commit sensibler Dateien |
| `.nojekyll` | Markierung für unveränderten Static-Site-Modus von Pages |

## Hinweise

Diese Plattform ist ein internes Recherche-Werkzeug eines
Abgeordnetenbüros des Deutschen Bundestages und dient der
parlamentarischen Untersuchung. Die enthaltenen Bewertungen und
Folgefragen folgen dem Grundsatz strikter Trennung zwischen
strukturellen, datenbasierten Befunden und inhaltlichen Bewertungen;
letztere werden nicht ohne formale Quellengrundlage geführt.
