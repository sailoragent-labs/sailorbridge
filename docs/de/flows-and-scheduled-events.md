[← SailorBridge](README.md)

# Abläufe und geplante Ereignisse

Ein Ablauf gibt deinem Team eine wiederholbare Methode für eine Aufgabe. Er hat einen Namen, den du im Chat eingeben kannst, sowie Schritte und Optionen, die für das Team gespeichert sind. Ein geplantes Ereignis sendet zu einem gewählten Zeitpunkt eine Nachricht in den Teamchat. Die Nachricht kann dem Leiter eine Frage stellen oder einen Ablauf starten.

## Einen Ablauf finden und ausführen

Gib im Teamchat `/` ein, um die aktivierten Abläufe und ihre Beschreibungen zu sehen. Wähle einen Ablauf, ergänze deinen Wunsch und sende die Nachricht. Zum Beispiel startet `/ask What should the export include?` ein Gespräch über diese Anforderung. Ein interaktiver Ablauf stellt Fragen im Chat. Ein Hintergrundablauf erscheint in **Auftragsliste**.

Wenn du einen Hintergrundablauf per Befehl startest, erstellt der **Leiter** normalerweise aus dem Gespräch eine Aufgabenbeschreibung und stellt den Auftrag in die Warteschlange. Ist **Direkt starten** für den Ablauf aktiv, wird dein Text direkt zur Aufgabenbeschreibung und der Auftrag wird sofort eingereiht. Bei integrierten Hintergrundabläufen ist diese Option standardmäßig aus. Schlägt der Leiter selbst einen Auftrag vor, wähle **Ja, Machen**, um ihn zu starten.

| Integrierter Ablauf | Verwendung und Ergebnis |
| --- | --- |
| `/ask` | Kläre eine Entscheidung. Beantworte jeweils eine Frage, um eine Zusammenfassung der Anforderungen zu erhalten. |
| `/plan` | Plane Arbeit mit mehreren Aufgaben. Lies den Plan und das vorgeschlagene Paket und wähle **Alle Aufgaben einreihen**, **Plan überarbeiten** oder **Vorerst nicht**. Der Plan ist selbst ein Auftrag, den du verfolgen kannst. |
| `/agent` | Gib einem Worker eine Routineaufgabe oder eine zeitaufwendige Aufgabe. Ein Worker erledigt sie und meldet das Ergebnis ohne Prüfrunde. |
| `/write-review` | Gib dem Team eine Umsetzungsaufgabe und sage, wie sie geprüft werden soll. Ein Schreiber erledigt die Arbeit, Prüfungen laufen und Schreiber und Prüfer sehen sich das Ergebnis an. |
| `/memory-tidy` | Prüfe das Team-Gedächtnis, entferne wertlos gewordene Einträge und führe Duplikate zusammen. Die Lieferung listet Aktionen und Vorschläge auf, die deine Entscheidung brauchen. Bei Bedarf kann das Team dies automatisch höchstens einmal in 24 Stunden ausführen. |
| `/docs-tidy` | Prüfe von Änderungen betroffene Dokumentation erneut und den Rest abwechselnd stichprobenartig. Die Lieferung weist Routinekorrekturen und Fragen an dich getrennt aus. |
| `/code-sweep` | Durchsuche Code nach Möglichkeiten zum Aufräumen. Lies die nummerierten Vorschläge in der Lieferung und sage dem Leiter, welche er ausführen soll. Die Suche selbst ändert nichts. |
| `/write-flow` und `/edit-flow` | Beschreibe eine wiederholbare Aufgabe, um einen Ablauf zu erstellen, oder gib an, wie sich ein vorhandener Ablauf ändern soll. Das Ergebnis wird für dein Team gespeichert. |

## Festlegen, wer schreibt und prüft

Öffne ⋯ im Teamchat, wähle **Team-Abläufe** und öffne `/write-review`. Die Seite zeigt die Schritte und Optionen für künftige Aufträge dieses Teams.

| Option | Verwendung |
| --- | --- |
| **Wer schreibt** | Behalte **Automatisch**, um einen Anbieter nach Aufgabenschwierigkeit zu wählen, oder wähle einen Motor für die Schreibschritte. |
| **Wer prüft** | Behalte **Automatisch**, um einen unabhängigen Prüfer aus einer anderen Modellfamilie zu suchen, oder wähle einen Motor für die Prüfung. Der Schreiber übernimmt seine Selbstprüfung. Die Modelleinstellungen des Teams bestimmen die tatsächlichen Modelle. |
| **Selbstprüfungen** | Wähle 0–10, Standard 3. In jeder Runde prüft der Schreiber seine Arbeit, behebt Befunde und prüft erneut, bis eine Prüfung nichts mehr findet oder das Limit erreicht ist. Mit 0 entfällt die Selbstprüfung. |
| **Wie viele Runden maximal** | Wähle 0–10, Standard 6. 0 wählt Solo. Dabei entfällt die unabhängige Prüfung und deine Einstellung für die Selbstprüfung bleibt gültig. |

Ein P1-Befund erfordert eine erneute Prüfung der gesamten Änderung. Bei weniger schwerwiegenden Befunden werden die Korrekturen geprüft. Ab Runde drei kann der Schreiber ohne P1 die übrigen Korrekturen abschließen und ohne weitere Prüfung liefern. Bleiben beim Rundenlimit P1-Befunde offen, stehen die Befunde, die den Auftrag angehalten haben, im **Lieferbericht**.

Damit Code gemergt werden kann, muss die vollständige anwendbare Prüfung auf dem letzten Commit bestehen. Gibt es für eine reine Dokumentationsänderung keine anwendbare Prüfung, muss ein unabhängiger Prüfer die Begründung akzeptieren. Im Solo-Modus bleibt eine Änderung ohne ausführbare Prüfung **Unvollständig**. [Prüfungen und Lieferung eines Auftrags lesen](jobs.md)

## Einen Team-Ablauf schreiben oder bearbeiten

1. Sende im Teamchat `/write-flow`, gefolgt von den Schritten, den Abschlusskriterien, dem Vorgehen bei einem fehlgeschlagenen Schritt und der erwarteten Lieferung. Zum Beispiel `/write-flow List Markdown files changed since the last commit. Report their paths. If none changed, say so.`
2. Braucht der Schreiber eine Entscheidung, beantworte die Frage im Chat. Sobald der Ablauf geschrieben und geprüft wurde, zeigt der Chat den gespeicherten Namen. Wähle **Ablauf ansehen**, um Beschreibung, Schritte und Optionen zu lesen. Der Name steht nun im Menü `/` zur Verfügung.
3. Wähle zum Überarbeiten **Im Chat bearbeiten** oder sende `/edit-flow <name> <change>`. Sage, was sich ändern und was bleiben soll. Beim Bearbeiten eines eigenen Ablaufs wird die Teamversion ersetzt. Beim Bearbeiten eines integrierten Ablaufs entsteht ein eigener Ablauf mit anderem Namen. In der Lieferung stehen die wirksamen Einstellungen und alle Schrittregeln, die bei der Änderung entfallen sind.

Du kannst die Optionen eines Ablaufs auch auf seiner Detailseite bearbeiten. Folgt der Ablauf gespeicherten Anweisungen, kannst du sie dort für die nächste Ausführung ändern. Schalte **Aktiviert** aus, um den Ablauf für neue Ausführungen aus dem Teammenü zu entfernen. Wartende und laufende Aufträge können abgeschlossen werden. Die beiden Befehle zum Schreiben von Abläufen bleiben verfügbar.

## Eine Nachricht planen

1. Öffne im Teammenü ⋯ den Punkt **Geplante Ereignisse** und nutze das Pluszeichen für **Ereignis hinzufügen**. Gib unter **Deine Anweisung** die zu sendende Nachricht ein, bis zu 16 KiB. Zum Beispiel `/docs-tidy Check the project documentation.`
2. Wähle **Häufigkeit**. Wähle **Einmalig** für ein künftiges lokales Datum mit Uhrzeit, **Täglich** für eine tägliche Uhrzeit oder **Werktags** für Montag bis Freitag. Lege bei **Alle paar Minuten** das **Intervall (Minuten)** auf 5 bis 720 fest. Begrenze es mit **Von** und **Bis** auf einen Teil des Tages.
3. Prüfe **Zeitzone**, die zunächst der Zeitzone deines Browsers entspricht, und speichere. Die Liste zeigt die erste Nachrichtenzeile und den nächsten Ausführungszeitpunkt. Mit dem Anlegen des Ereignisses genehmigst du die Nachricht. Zur gewählten Zeit erscheint sie im Chat unter deinem Namen mit der Kennzeichnung **Geplant**. Jede Auslösung zählt als vollständiger Chatturn des Leiters.

Die Zeiten richten sich nach der gewählten Zeitzone. Überspringt eine Zeitumstellung eine geplante Uhrzeit, nutzt das Ereignis die nächste gültige Zeit. Tritt dieselbe Uhrzeit zweimal auf, zählt das erste Vorkommen. Bei einem Intervall mit Zeitfenster entfallen Ausführungen außerhalb des Fensters.

Öffne das Ereignis, um Nachricht oder Zeitplan zu ändern. Beim Speichern wird die nächste Ausführung neu berechnet. Deaktiviere das Ereignis, um künftige Nachrichten zu stoppen, und aktiviere es wieder, wenn es weitergehen soll. Die erneute Aktivierung gilt ab diesem Zeitpunkt. Nach einem Ausfall des Planungsdienstes wird nur die letzte verpasste Nachricht gesendet. Suche ein Ereignis per Text oder genauer Nummer, etwa `#6`. Nutze **Abgeschlossen**, um ein beendetes einmaliges Ereignis zu finden.

## Wenn es nicht funktioniert

- Erkennt der Chat einen Ablauf nicht, gib `/` ein, um die aktivierten Namen dieses Teams zu sehen. Aktiviere den Ablauf bei Bedarf unter **Team-Abläufe** erneut. Kann ein Plan sein Aufgabenpaket nicht einreihen, weil `/write-review` deaktiviert ist, aktiviere den Ablauf vor dem erneuten Einreichen.
- Ein Team kann 30 eigene Abläufe haben. Lösche am Limit einen nicht mehr benötigten eigenen Ablauf, bevor du einen neuen erstellst. Ist ein Name bereits vergeben, bearbeite den zugehörigen Ablauf oder wähle einen neuen Namen. Meldet eine Änderung, dass eine entfallene Schrittregel zu lang für die Lieferung ist, kürze oder verschiebe die Regel auf der Ablaufseite und versuche die Änderung erneut.
- Ein Team kann bis zu 20 geplante Ereignisse haben. Lösche am Limit ein Ereignis, bevor du eines hinzufügst. Ist ein einmaliges Ereignis bereits gelaufen, lege für eine Wiederholung ein neues an. Verwende einen künftigen Zeitpunkt und ein Intervall im angegebenen Bereich.
- Nennt eine geplante Nachricht einen fehlenden oder deaktivierten Ablauf oder einen fehlenden nummerierten Eintrag, ist diese Ausführung verbraucht. Korrigiere die Nachricht oder aktiviere den Ablauf vor dem nächsten Termin. Meldet ein geplanter interaktiver Ablauf, dass bereits ein anderer läuft, wartet er auf eine spätere Auslösung.
