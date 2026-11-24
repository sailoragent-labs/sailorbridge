[English](../../AGENTS.md) · [简体中文](../zh-CN/AGENTS.md) · [日本語](../ja/AGENTS.md) · [한국어](../ko/AGENTS.md) · [Deutsch](AGENTS.md) · [Français](../fr/AGENTS.md) · [Español](../es/AGENTS.md) · [Português (BR)](../pt-BR/AGENTS.md) · [Bahasa Indonesia](../id/AGENTS.md) · [हिन्दी](../hi/AGENTS.md)

# SailorBridge einrichten

## 1. Rechner vorbereiten

Verwende einen eigenen Rechner mit Linux x64 oder macOS auf arm64 oder x64. Installiere Git und entweder Claude Code oder Codex. Melde dich mit deinem eigenen Konto beim Motor an und wähle das Projektverzeichnis für dein Team.

**Prüfung** — `git --version` und je nach Motor `claude --version` oder `codex --version` geben jeweils eine Version aus. Ist der Motor installiert, aber noch nicht angemeldet, führe auf diesem Rechner `claude login` oder `codex login` aus. Du kannst den Rechner schon vorher koppeln. Melde dich vor dem ersten Chat oder Auftrag beim Motor an.

## 2. Im Browser registrieren

Öffne die [App](https://app.sailorbridge.com) und wähle **Registrieren**. Gib für diesen Einstieg eine verfügbare numerische Kapitän-ID ein, die als kostenlos angezeigt wird, lege ein Passwort fest, bestätige dein Alter und akzeptiere die Nutzungsbedingungen.

**Prüfung** — Die App öffnet sich und du kannst **Rechner** aufrufen.

## 3. Installationsbefehl ausführen

Öffne unter **Rechner** die Seite **Neuen Rechner koppeln**. Kopiere den dort angezeigten Installationsbefehl und führe ihn auf dem Rechner aus Schritt 1 aus. Er installiert `sail` und startet die Kopplung automatisch.

**Prüfung** — Im Terminal siehst du einen achtstelligen Pairing-Code und die verbleibende Zeit. Läuft der Code ab, erhältst du mit `sail login` einen neuen.

- **Schon mit dieser Adresse gekoppelt?** Prüfe die Verbindung mit `sail host status`. Besteht sie, fahre mit Schritt 5 fort. Um den Dienst an derselben Adresse wiederherzustellen, führe `sail login` aus. Der Dienst startet mit den vorhandenen Zugangsdaten neu.
- **Falsche Adresse (`origin_mismatch`)?** Zum Wechseln führe `sail uninstall` aus. Kopiere dann den Installationsbefehl von der Rechnerseite der gewünschten App und führe ihn aus. Die Deinstallation löscht die lokalen Daten von SailorBridge einschließlich seiner Arbeitskopien.

## 4. Rechner genehmigen

Gib den Pairing-Code auf der Kopplungsseite im Browser ein und wähle **Koppeln**. Vergleiche Rechnernamen und **Schlüssel-Code** mit der Anzeige im Terminal. Lies und bestätige beim ersten Koppeln den Hinweis zu den Rechten des Benutzers, der `sail` ausführt. Wähle dann **Rechner genehmigen**.

**Prüfung** — Warte, bis unter **Rechner** der Status **Online** erscheint. Auch das Terminal bestätigt, dass der Rechner gekoppelt und online ist.

## 5. Team erstellen

Wähle **Team Erstellen**. Gib dem Team einen Namen, wähle den verbundenen Rechner und trage unter **Projektverzeichnis** den absoluten Pfad auf diesem Rechner ein. Fehlt das Verzeichnis, legt SailorBridge es bei der ersten Verwendung an. Wähle unter **Ziel** den Standard **Auto-Merge**, um Änderungen in den Hauptbranch des Remotes zu übernehmen, oder **Branch**, um jeden Auftrag zur Prüfung in einen eigenen Branch zu pushen. Erstelle das Team.

**Prüfung** — Der gewählte Rechner wird im neuen Team als **Online** angezeigt.

## 6. Erste Nachricht senden

Öffne den **Chat** des Teams und frage „In welchem Projektverzeichnis arbeiten wir?“

**Prüfung** — Der **Leiter** antwortet im selben Chat.

## 7. Ersten Auftrag abschließen

Sende im Teamchat `/agent Zähle die Dateien direkt im Projektverzeichnis und nenne mir die Anzahl.` Öffne **⋯ → Auftragsliste**, um den Auftrag zu verfolgen.

**Prüfung** — Beim Auftrag steht **Fertig**. Öffne den **Lieferbericht** und lies die Anzahl der Dateien.
