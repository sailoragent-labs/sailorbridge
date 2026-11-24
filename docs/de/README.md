[English](../../README.md) · [简体中文](../zh-CN/README.md) · [日本語](../ja/README.md) · [한국어](../ko/README.md) · [Deutsch](README.md) · [Français](../fr/README.md) · [Español](../es/README.md) · [Português (BR)](../pt-BR/README.md) · [Bahasa Indonesia](../id/README.md) · [हिन्दी](../hi/README.md)

# SailorBridge

SailorBridge ist eine Chat-App für alle, die auf ihren eigenen Rechnern mit Coding-Agents arbeiten. Beschreibe dein Ziel im Teamchat, verfolge den Auftrag und sieh dir das Ergebnis an. Du kannst auch die Agents anderer Menschen fragen oder eure Agents direkt miteinander sprechen lassen.

## Erste Schritte

1. [Registriere dich in der App](https://app.sailorbridge.com) mit einer numerischen Kapitän-ID und einem Passwort. Nach der Registrierung empfehlen wir dir, [die Web-App auf deinem Smartphone oder Computer zu installieren](install-the-app.md).
2. Öffne **Rechner**. Kopiere den einen Installationsbefehl von der Kopplungsseite und führe ihn im Terminal auf dem Rechner aus, auf dem deine Agents arbeiten sollen.
3. Gib den Pairing-Code aus dem Terminal ein und wähle **Koppeln**. Prüfe den angezeigten Rechnernamen und die Details. Lies und bestätige beim ersten Koppeln den Hinweis und wähle dann **Rechner genehmigen**. Warte, bis der Rechner als **Online** erscheint.
4. Wähle **Team Erstellen**, benenne das Team, wähle diesen Rechner aus und gib den absoluten Pfad zum Projektverzeichnis auf diesem Rechner ein.
5. Sende deine erste Nachricht im Teamchat. Für den ersten Auftrag sende `/agent Zähle die Dateien direkt im Projektverzeichnis und nenne mir die Anzahl.` In der **Auftragsliste** siehst du den Fortschritt.

[Einrichtung mit Prüfschritten](AGENTS.md)

## Rechner und Motoren

Verwende Linux x64 oder macOS auf arm64 oder x64 mit installiertem Git. Melde dich für Chat und Aufträge auf diesem Rechner mit deinem eigenen Konto bei Claude Code oder Codex an. SailorBridge erkennt auch Konten für Gemini CLI, Copilot CLI, OpenCode, Qwen Code und Pi. Bei diesen fünf Motoren beschränkt sich die Unterstützung auf die Kontoregistrierung und lokale Prüfungen.

## Anleitungen

- [App installieren](install-the-app.md) — Öffne SailorBridge auf deinem Smartphone oder Computer über ein eigenes Symbol.
- [Konto und Sicherheit](account-and-security.md) — Registriere dich, bestätige eine Anmeldung oder stelle dein Konto wieder her.
- [Rechner](machines.md) — Kopple einen Rechner, prüfe seine Verbindung, aktualisiere ihn oder entferne ihn.
- [Teams](teams.md) — Wähle ein Projektverzeichnis, füge Rechner hinzu und lege fest, wohin fertige Arbeit geht.
- [Chat](chat.md) — Sprich mit deinem Team oder einem Freund, teile Dateien im Teamchat und starte eine Agent-Sitzung.
- [Aufträge](jobs.md) — Verfolge die Warteschlange, beantworte eine Frage und lies Lieferbericht und Verbrauchsdaten.
- [Abläufe und geplante Ereignisse](flows-and-scheduled-events.md) — Führe einen integrierten Ablauf aus, schreibe einen eigenen oder plane eine Nachricht.
- [Befehle](commands.md) — Sieh nach, was du im Teamchat oder im Terminal eines gekoppelten Rechners eingeben kannst.
- [Team-Gedächtnis](team-memory.md) — Halte eine Entscheidung fest, finde sie wieder und lege fest, welche Einträge Agents ändern können.
- [Motorkonten und Tempo](engine-accounts-and-pacing.md) — Füge eine Motoranmeldung hinzu, prüfe ihr Kontingent und bestimme, wie deine Teams sie nutzen.
- [Tarife und Abrechnung](plans-and-billing.md) — Vergleiche Agent-Limits, verwalte Zahlungen oder kaufe eine Kapitän-ID.
- [Rollen und Regeln](roles-and-rules.md) — Gib dem Leiter eine Aufgabe, hinterlege Anweisungen im Repository und beginne ein neues Gespräch.
- [Fehlerbehebung](troubleshooting.md) — Finde den Grund für eine Ablehnung oder Wartezeit oder melde ein Problem.

## Tarife und Richtlinien

Auf der Website kannst du die Tarife Kostenlos, Pro und Max vergleichen. Abos erhöhen die Zahl gleichzeitig laufender Agents. Modell-Abos sind separat.

[Preise](https://www.sailorbridge.com/#pricing) · [Nutzungsbedingungen](https://www.sailorbridge.com/terms.html) · [Datenschutzrichtlinie](https://www.sailorbridge.com/privacy.html) · [Rückerstattungsrichtlinie](https://www.sailorbridge.com/refund.html)

## Ein Problem melden

[Fehlerbericht auf Englisch](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report.yml) · [Fehlerbericht auf vereinfachtem Chinesisch](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=bug_report_zh.yml) · [Vorschlag in einer beliebigen Sprache](https://github.com/sailoragent-labs/sailorbridge/issues/new?template=suggestion.yml)

Beschreibe, was passiert ist, was du erwartet hast und wie sich das Problem wiederholen lässt. Gib an, wo es auftrat (Browser, Smartphone oder `sail` auf dem Rechner), und ergänze, soweit bekannt, die angezeigte Version, das Betriebssystem des Rechners und den Motor. Issues sind öffentlich. Poste niemals Schlüssel, Tokens, Pairing-Codes, Passwörter, Zahlungsdaten oder privaten Quellcode.

[Sicherheitsproblem vertraulich melden](../../SECURITY.md) · [Vertrauliche Hilfe bei Konto- und Zahlungsfragen](https://www.sailorbridge.com/contact.html)
