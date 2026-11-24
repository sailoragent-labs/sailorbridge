[← SailorBridge](README.md)

# Rechner

Ein Rechner ist ein Computer, den du mit deinem Konto verbindest, damit er einen Teamleiter ausführen oder Aufträge übernehmen kann. Installiere `sail` auf jedem Rechner und genehmige ihn im Browser. Der Hintergrunddienst hält die Verbindung aufrecht, wenn du das Terminal schließt.

## Einen Rechner installieren und koppeln

1. Verwende einen Rechner, den du kontrollierst, mit Linux x64 oder macOS auf arm64 oder x64. Installiere Git. Für Chats und Aufträge installiere Claude Code oder Codex und melde dich auf diesem Rechner mit deinem eigenen Motorkonto an. Du kannst das Koppeln vor der Anmeldung beim Motor abschließen.
2. Öffne in der App **Rechner** und dann **Neuen Rechner koppeln**. Kopiere den angezeigten Installationsbefehl in ein Terminal auf dem Rechner, den du verbinden willst. Du kannst ihn in jedem Verzeichnis ausführen. Er installiert `sail`, startet die Kopplung und zeigt einen achtstelligen Code an, der 10 Minuten lang gültig ist.
3. Gib den Code im Browser unter **Pairing-Code** ein und wähle **Koppeln**. Vergleiche Rechnernamen und **Schlüssel-Code** mit der Anzeige im Terminal. Lies bei der ersten Kopplung den Hinweis, bevor du ihn akzeptierst. Agents können Dateien lesen, ändern und löschen, Zugangsdaten nutzen und mit den Betriebssystemrechten des Benutzers, der `sail` ausführt, auf das Netzwerk zugreifen. Nutze für eine isolierte Umgebung einen eigenen Rechner oder Container.
4. Wähle **Rechner genehmigen**. Lass den Rechner verbunden, während er seine Zugangsdaten abruft und den Dienst startet. Wenn unter **Rechner** der Status **Online** erscheint und das Terminal die Verbindung bestätigt, kannst du **Konten Einrichten** oder **Team Erstellen** wählen. [Team erstellen](teams.md)

## Die Verbindung prüfen oder weitere Rechner koppeln

Öffne einen Rechner unter **Rechner**. Dort siehst du seinen Namen, seine Plattform, **Zuletzt online**, **Gekoppelt am** und **Client-Version**. Ändere bei Bedarf den Namen, um Rechner besser zu unterscheiden. Führe auf dem Rechner `sail host status` aus, um Kopplung, Verbindung und Dienststatus zu prüfen und das lokale Log zu finden.

Wenn du einen weiteren Computer verwenden willst, öffne **Neuen Rechner koppeln** erneut und führe den angezeigten Befehl auf diesem Computer aus. Sobald er online ist, füge ihn dem Team hinzu und lege dort seinen Projektordner fest. Ein Rechner kann mehreren Teams dienen. Jeder Auftrag läuft auf einem geeigneten Rechner seines Teams. [Rechner eines Teams verwalten](teams.md)

## Eine Installation aktualisieren oder reparieren

Automatische Updates sind standardmäßig aktiv. Nach der Prüfung eines Updates startet der Dienst neu und nimmt lokale Arbeit wieder auf. Abgeschlossene Schritte bleiben erhalten. Ein unterbrochener lokaler Schritt kann erneut laufen. Für ein manuelles Update führe `sail upgrade` auf dem Rechner aus. Die Ausgabe zeigt, ob ein Update installiert wurde, die Version bereits aktuell war oder ein Fehler aufgetreten ist. Prüfe die installierte Version mit `sail --version`.

Wenn der Dienst wiederhergestellt werden muss, führe `sail login` aus. An derselben Adresse installiert der Befehl den Dienst erneut und startet ihn mit den vorhandenen Zugangsdaten neu. Werden sie abgelehnt und ist der Rechner noch registriert, startet eine erneute Kopplung zur Reparatur. Im Browser erscheint **Vorhandenen Rechner erneut koppeln** mit dem Rechner, der ersetzt wird. Prüfe die Angaben und genehmige den neuen Code. Der Rechner behält seine Teams. Für die Passwortwiederherstellung gilt der Erhalt der neuen Zugangsdaten als neues Kopplungsdatum.

## Einen Rechner ausmustern oder die Installation entfernen

Um einen Rechner für dein gesamtes Konto auszumustern, öffne sein Zeilenmenü unter **Rechner**, wähle **Löschen** und bestätige. Seine Zugangsdaten werden widerrufen. Er verlässt seine Teams und stellt die Arbeit ein, sobald ihn die Mitteilung erreicht. Ist er verbunden, geschieht das sofort, sonst bei der nächsten Verbindung. Lokale Arbeitskopien bleiben erhalten. Um ihn wieder zu verwenden, führe dort `sail login` aus, genehmige die neue Kopplung und füge ihn den Teams hinzu, die ihn brauchen.

Um SailorBridge vom Computer zu entfernen, sichere zuerst benötigte Arbeit aus seinen SailorBridge-Arbeitskopien. Führe dort `sail uninstall` aus. Der Befehl stoppt den Dienst und entfernt `sail`, die Dienstdefinition, den Shell-Pfadeintrag des Installers und das gesamte Verzeichnis `~/.sailorbridge/`. Dazu gehören Zugangsdaten, Kontoregistrierungen, Logs, lokale Chatverläufe, Arbeitskopien und die Sicherungskopie von `sail`. Deine Projektverzeichnisse und die Anmeldeverzeichnisse der Motoren bleiben erhalten. Zur Neuinstallation verwende den Befehl unter **Neuen Rechner koppeln**.

## Wenn es nicht funktioniert

- Meldet die Kopplung, dass Git fehlt, installiere Git und fahre mit `sail login` fort. Eine fehlende Motoranmeldung kannst du vor dem ersten Chat oder Auftrag separat mit `claude login` oder `codex login` nachholen.
- Läuft der Code ab, fordere mit `sail login` einen neuen an. Stimmt der Rechnername oder der **Schlüssel-Code** nicht überein, wähle **Kopplung abbrechen** und prüfe das Terminal auf dem vorgesehenen Rechner. War die Genehmigung erfolgreich, aber der Rechner hat sich nach 10 Minuten noch nicht verbunden, führe `sail host status` und dann `sail login` aus, um die Verbindung wiederherzustellen.
- Geht ein Rechner unerwartet offline, prüfe sein Netzwerk und den Dienst mit `sail host status`. Standardmäßig gilt ein Rechner nach 90 Sekunden als offline. Die Benachrichtigung erscheint erst nach 10 Minuten ohne Verbindung und verschwindet, sobald er wieder online ist.
- Scheitert ein Update, öffne den Rechner, lies den Grund und führe den angezeigten Reparaturbefehl als der Benutzer aus, der `sail` installiert hat. Lässt sich die lokale Sicherung nicht verwenden, nutze den Installationsbefehl von der Kopplungsseite.
- Meldet der Rechner eine geänderte Serveridentität, lehnt er die Verbindung ab. Prüfe den gespeicherten Fingerabdruck auf dem Rechner mit `sail host status --trust`. Wenn du die Änderung erwartet hast, führe `sail login` aus, prüfe den neuen Fingerabdruck im Terminal und genehmige eine neue Kopplung.
- Meldet `sail login` den Fehler `origin_mismatch`, nutze vor dem Adresswechsel das oben beschriebene Verfahren zur Deinstallation. Kopiere dann den Installationsbefehl von der Seite **Rechner** der gewünschten App. Auch bei unlesbaren lokalen Kopplungsdaten musst du deinstallieren und neu koppeln.
- Meldet `sail uninstall`, dass der Dienst die Ausmusterung nicht bestätigen konnte, sind die lokalen Dateien bereits entfernt. Öffne **Rechner** und mustere den Eintrag dort aus.
