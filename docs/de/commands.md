[← SailorBridge](README.md)

# Befehle

Gib dem **Leiter** im Teamchat eine Aufgabe oder starte einen Ablauf. Verwende `sail` im Terminal, um den Rechner zu verwalten, auf dem es installiert ist, die Arbeit des Teams einzusehen oder einen Befehl auf einem anderen Rechner desselben Teams auszuführen.

## Einen Befehl im Teamchat wählen

Öffne den **Chat** deines Teams und gib `/` ein. Das Menü zeigt vier Kurzbefehle, die aktivierten Abläufe des Teams und zuletzt `/clear`. Wähle einen Eintrag, ergänze deine Anfrage in deiner eigenen Sprache und sende sie. Die Befehlsnamen bleiben auf Englisch. Die Auswahl von `/clear` wirkt sofort.

| Eingabe | Was passiert |
| --- | --- |
| `/job #12 What is this waiting for?` | Der **Leiter** erhält Auftrag 12 und deine Frage. |
| `/event #6 Move this to weekdays.` | Der **Leiter** erhält das geplante Ereignis 6 und deine gewünschte Änderung. |
| `/memory #3 When does this apply?` | Der **Leiter** erhält den Gedächtniseintrag 3 und deine Frage. |
| `/do Check the current branch.` | Der **Leiter** erledigt die Arbeit in diesem Chatturn und meldet das Ergebnis samt allem, was nicht möglich war. |
| `/clear` | Blendet frühere Nachrichten in diesem Teamchat aus und startet ein neues Gespräch. |

Verwende die Nummer aus der passenden Liste des Teams. Aufträge, Ereignisse und Gedächtniseinträge haben jeweils eigene Nummern. **Zum Chat** auf einer Detailseite trägt den richtigen Kurzbefehl und die Nummer für dich ein. Um einen Rechner zu nennen, gib `@` ein und wähle ihn aus der Teamliste.

## Einen Ablauf per Namen ausführen

| Befehl | Ergebnis |
| --- | --- |
| `/ask` | Jeweils eine Frage, danach eine Zusammenfassung der Anforderungen im Chat. |
| `/plan` | Ein Planungsauftrag. Lies den Plan und entscheide, ob du die vorgeschlagenen Aufgaben einreihst. |
| `/agent` | Ein Worker erledigt die Aufgabe und meldet das Ergebnis. |
| `/write-review` | Ein Schreiber erledigt die Arbeit, führt Prüfungen aus und überarbeitet sie gemäß den Prüfeinstellungen des Ablaufs. |
| `/memory-tidy` | Ein Auftrag, der Einträge im Team-Gedächtnis prüft, zusammenführt oder entfernt. |
| `/docs-tidy` | Ein Auftrag, der Projektdokumente prüft und Punkte meldet, die deine Entscheidung brauchen. |
| `/code-sweep` | Eine Prüfung im Lesemodus mit nummerierten Aufräumaufgaben, die du zur Ausführung auswählen kannst. |
| `/write-flow` | Beschreibe eine wiederholbare Aufgabe. Nach erfolgreichem Abschluss wird der neue Ablauf in diesem Team gespeichert. |
| `/edit-flow` | Nenne den Ablauf und die Änderung. Eine erfolgreiche Änderung ersetzt einen eigenen Ablauf. Beim Bearbeiten eines integrierten Ablaufs entsteht ein eigener unter neuem Namen. |

Sende zum Beispiel `/agent Count the top-level files in this project.` Wenn du einen Hintergrundablauf selbst sendest, genehmigst du den Auftrag. Der **Leiter** schreibt die Aufgabenbeschreibung anhand des Gesprächs. Ist **Direkt starten** aktiv, kommt dein Text direkt in die Warteschlange. Öffne **Details** in der Chatzeile des Auftrags, um ihn zu verfolgen. Wenn der **Leiter** im normalen Chat einen Hintergrundablauf vorschlägt, lies die Karte und wähle **Ja, Machen**, um ihn zu starten. [Abläufe und geplante Ereignisse](flows-and-scheduled-events.md)

## Einen Rechner koppeln, prüfen oder entfernen

| Terminalbefehl | Wann du ihn nutzt |
| --- | --- |
| `sail login` | Der Installationsbefehl führt ihn für dich aus. Führe ihn für einen neuen Kopplungscode oder zur Wiederherstellung des Dienstes an derselben Adresse mit vorhandenen Zugangsdaten erneut aus. |
| `sail host status` | Prüfe Kopplung, Verbindung, Dienst, Version und Speicherort des Logs. Ergänze `--trust`, um den gespeicherten Fingerabdruck des Serverschlüssels zu sehen. |
| `sail --version` | Zeigt die installierte Version. |
| `sail upgrade` | Sucht jetzt nach einem Update. Das Ergebnis zeigt, ob eine neue Version installiert wurde, die Version schon aktuell war oder das Update scheiterte. |
| `sail host service status` | Prüfe den Hintergrunddienst. Verwende `sail host service install`, `sail host service restart` oder `sail host service stop` zum Installieren, Neustarten oder Stoppen. |
| `sail host run` | Führe den Rechnerdienst im Vordergrund aus, wenn keine weitere Instanz läuft. |
| `sail confirm` | Hole für **Bestätige, dass du es bist** im Terminal eines gekoppelten Rechners einen einmaligen Anmeldecode. |
| `sail recover` | Hole für **Passwort vergessen?** deine Kapitän-ID und einen einmaligen Wiederherstellungscode im Terminal eines gekoppelten Rechners. |
| `sail uninstall` | Entferne SailorBridge und seine lokalen Daten einschließlich Arbeitskopien und Logs. Deine Projektverzeichnisse und Motoranmeldungen bleiben erhalten. |

Für Motoranmeldungen zeigt `sail account list`, was dieser Rechner erkennt. Nutze `sail account add <name> <directory>`, um ein Anmeldeverzeichnis zu registrieren, `sail account remove <name>`, um eine Registrierung zu entfernen oder eine Standardanmeldung zu ignorieren, und `sail account restore <provider>`, um eine ignorierte Standardanmeldung wieder zu erkennen. Für einen kompatiblen Endpunkt schreibt `sail account create <provider>` eine Einstellungsvorlage unter `~/.sailorbridge/`, die `sail uninstall` entfernt. [Ein Konto für GLM, DeepSeek oder Kimi aus einer Vorlage einrichten](engine-accounts-and-pacing.md#ein-konto-für-glm-deepseek-oder-kimi-aus-einer-vorlage-einrichten)

## Mit nummerierten Einträgen eines Teams arbeiten

Führe die folgenden Befehle im Terminal auf einem gekoppelten Rechner im konfigurierten Projektverzeichnis des Teams aus. Verwende die Eintragsnummern deines Teams. Der Auftrag `#12` im Chat wird im Terminalbefehl zum Beispiel als `12` angegeben.

| Aufgabe | Befehle für dein Terminal |
| --- | --- |
| Einen Auftrag finden | `sail job list` listet offene Aufträge. Ergänze `--all`, um beendete Aufträge einzubeziehen. `sail job get 12` zeigt Auftrag 12. Ergänze `--json` für alle Details. |
| Einen Auftrag stoppen oder löschen | `sail job stop 12` stoppt den Auftrag. `sail job delete 12` löscht den Eintrag eines beendeten Auftrags. |
| Ein Ereignis finden | `sail event list` listet aktivierte Ereignisse, die noch ausgeführt werden sollen. Ergänze `--all`, um deaktivierte oder abgeschlossene einzubeziehen. `sail event get 6` zeigt Nachricht und Zeitplan. |
| Ein Ereignis löschen | `sail event delete 6` entfernt das geplante Ereignis. |
| Einen Gedächtniseintrag löschen | `sail memory delete 3` löscht einen Eintrag dauerhaft. Einen gesperrten Eintrag löschst du in der App unter **Team-Gedächtnis**. |

Die folgenden Befehle brauchen eine aktive Sitzung des **Leiter** oder einen Auftrag. Im Terminal geben sie selbst im Teamverzeichnis `local_team_context_missing` zurück. Bitte den **Leiter** im Teamchat um das Gewünschte. Um selbst mit einem vorhandenen Eintrag zu arbeiten, öffne in der App **Auftragsliste**, **Geplante Ereignisse** oder **Team-Gedächtnis**. Worker haben nur Lesezugriff auf Aufträge und Ereignisse.

| Wer führt es aus? | Aufgabe und Befehle |
| --- | --- |
| **Leiter** | `sail job create <flow> "<task>"` reiht einen Hintergrundablauf ein. `sail job edit 12 "<revised task>"` ändert einen offenen Auftrag. `sail job retry 12` setzt geeignete Arbeit unter derselben Nummer fort. |
| **Leiter** | `sail event create "Check the queue" --weekdays 09:00` plant eine Teamchat-Nachricht in der Zeitzone des Rechners. Andere Zeitpläne verwenden `--once`, `--daily` oder `--every`. Mit `--tz` legst du eine Zeitzone fest. `sail event edit 6 --disable` pausiert das Ereignis. |
| **Leiter** oder Worker | `sail memory list` listet Einträge. `sail memory titles` listet Titel. `sail memory search "release checklist"` gibt bis zu 10 Treffer zurück. `sail memory get 3` liest den Eintrag. |
| **Leiter** oder Worker | `sail memory create "<title>" "<body>"` speichert einen Fakt oder reicht eine Korrektur unter demselben Titel ein. `sail memory edit 3 "<body>"` ändert einen Eintrag. `sail memory conflicts` listet ungelöste Konflikte. |
| **Leiter** | `sail memory resolve <id> --value "<correct text>"` löst einen Konflikt anhand seiner Konflikt-ID. Bei einem gesperrten Eintrag entscheidest du unter **Team-Gedächtnis**. |
| **Leiter** oder Worker | `sail memory list --tidy` listet Kandidaten und Versionen. `sail memory review 3 --rev <version>` markiert einen Eintrag als erhaltenswert. `sail memory merge` nimmt wiederholte Argumente `--entry <id>:<version>` sowie `--title` und `--body` entgegen. Von den Worker-Aufträgen darf nur `/memory-tidy` Einträge löschen. |

Meldet ein Befehl eine ausstehende Entscheidung, prüfe den aktuellen Wert in der Antwort, bevor du davon ausgehst, dass die Änderung wirksam wurde.

## Einen Befehl lokal oder auf einem anderen Teamrechner ausführen

Bei einem lokalen Befehl gibt `sail run git status` die Ausgabe im Terminal aus. Setze bei einem langen, nicht interaktiven Befehl `--fold` vor den Befehl. Du erhältst das Ergebnis, die letzten Ausgabezeilen und den Pfad zum vollständigen Log. Für ein lokales tmux-Fenster zeigt `sail tmux read <window>` seinen Text. `sail tmux send <window> "<text>"` füllt das Eingabefeld. Sende `sail tmux send <window> --key Enter`, wenn du die Eingabe abschicken willst.

Um einen Befehl auf einem anderen eigenen Rechner im selben Team auszuführen, beginne im Teamverzeichnis und ersetze `build-machine` durch den Namen des Zielrechners. Beispielsweise läuft `sail exec build-machine git status --short` auf dem Zielrechner im Verzeichnis dieses Teams. Der Exitcode und die letzten 40 Zeilen der kombinierten Ausgabe, bis zu 16 KiB, erscheinen im Terminal. Setze `--json` vor den Rechnernamen, um ein einzelnes JSON-Ergebnis zu erhalten.

Das Standardzeitlimit beträgt 5 Minuten. Setze zum Ändern `--timeout` und eine positive Sekundenzahl vor den Rechnernamen. Ein sendender Rechner kann bei bis zu 8 Befehlen auf Ergebnisse warten. Ctrl-C beendet die Wartezeit im Terminal. Der entfernte Befehl kann weiterlaufen.

## Wenn es nicht funktioniert

- Ist ein Chatbefehl unbekannt, gib `/` ein und wähle einen aktivierten Ablauf. Verweist eine alte Bestätigungskarte auf einen deaktivierten Ablauf, aktiviere ihn unter **Team-Abläufe** oder wähle einen verfügbaren Ablauf und sende eine neue Anfrage.
- Wird ein nummerierter Kurzbefehl nicht gefunden, öffne **Auftragsliste**, **Geplante Ereignisse** oder **Team-Gedächtnis** für dieses Team. Prüfe die Nummer und gib im Chat auch `#` ein.
- Kann `sail exec` das Team nicht erkennen, wechsle in eines der angezeigten Teamverzeichnisse. Ist der Zielrechner offline oder nimmt er keine Arbeit mehr an, versuche es erneut, sobald er online ist und Arbeit annimmt. Ein Zielrechner hat online bis zu 10 Minuten zur Übernahme eines wartenden Befehls. Geht er vorher offline, wartet der Befehl 60 Sekunden auf die Wiederverbindung. Verschwindet der Zielrechner nach dem Start, prüfe, was der Befehl getan hat, bevor du ihn erneut ausführst.
