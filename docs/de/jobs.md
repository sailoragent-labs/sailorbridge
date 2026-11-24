[← SailorBridge](README.md)

# Aufträge

Ein Auftrag ist eine Ausführung eines Ablaufs. Jedes Team hat eine Warteschlange für alle seine Rechner. Im Chat kannst du dem Team einen Auftrag geben, seinen Fortschritt anhand der Nummer nachsehen und seine Lieferung öffnen, um das Ergebnis und offene Punkte zu sehen.

## Arbeit in die Warteschlange stellen

Sende im Teamchat einen Ablaufnamen und eine Aufgabe, zum Beispiel `/agent Count the files at the top level of this project and report the count.` Der Auftrag kommt in die Warteschlange. Ein geeigneter Rechner übernimmt ihn, sobald er freie Kapazität hat. Der Rechner führt den Auftrag in seiner eigenen Arbeitskopie aus.

Wenn der **Leiter** im Gespräch Arbeit vorschlägt, lies den Vorschlag und wähle **Ja, Machen**, um sie einzureihen. Bei einem Plan mit mehreren Aufgaben lies die Liste, bevor du **Alle Aufgaben einreihen** wählst. Mit **Plan überarbeiten** kannst du eine Änderung beschreiben. Mit **Vorerst nicht** bleibt das Paket außerhalb der Warteschlange. Nach der Annahme erhält jede Aufgabe eine eigene Auftragsnummer. [Einen Ablauf wählen](flows-and-scheduled-events.md)

## Einen Auftrag finden und seinen Status lesen

Öffne das Menü ⋯ im Teamchat und wähle **Auftragsliste** oder wähle **Details** am Auftrag im Chat. Die Liste zeigt zunächst **Läuft** und merkt sich dann deinen letzten Filter in diesem Browser. Wähle **Alle**, um beendete Aufträge einzubeziehen. Suche nach Aufgabentext oder Ablaufnamen oder gib die vollständige Nummer mit Raute ein, etwa `#6`, um sie über alle Filter hinweg zu finden.

| Anzeige | Bedeutung |
| --- | --- |
| **Wartet** | Der Auftrag wartet auf die Übernahme. Die Zeile darunter nennt den Grund. Eine dort genannte Auftragsnummer verweist auf einen vorausgesetzten Auftrag. |
| **Läuft** | Ein Rechner hat den Auftrag übernommen. Öffne ihn, um den aktuellen Schritt und den Rechner zu sehen. |
| **Wartet auf den Leiter** oder **Wartet auf dich** | Der Leiter beantwortet Fragen, die er selbst klären kann. Braucht er deine Entscheidung, wähle **Antworten** und antworte im Chat. Der Filter **Du** findet Aufträge, die auf dich warten. |
| **Fertig** | Der Ablauf hat sein Ergebnis geliefert. **Erledigt, Prüfungen fehlgeschlagen** zeigt eine Lieferung mit einer fehlgeschlagenen Prüfung an. Lies die Prüfung, bevor du das Ergebnis nutzt. |
| **Unvollständig** | Der Ablauf endete, bevor alles Angeforderte geliefert war. Lies, wo er endete und was fehlt. Erstellte Arbeit bleibt erhalten. |
| **Fehler** | Ein Fehler hat die Ausführung beendet. Öffne den Bericht und **Notiz der Maschine**, um den Grund zu sehen. |
| **Storniert** | Der Auftrag wurde gestoppt. Sein Eintrag bleibt in der Liste verfügbar. |

Auch **Pausiert** und **Kontingent** können erklären, warum ein Auftrag gerade nicht läuft. Öffne **Warum er nicht läuft**, um zu sehen, worauf er wartet und was du gegebenenfalls tun kannst.

## Auftrag, Lieferung und Verbrauch lesen

Wähle die nummerierte Zeile. **Auftragsdetails** zeigt Status, **Laufzeit** und **Runden**. Unter **Aufgabeninformationen** stehen der Rechner, wer den Auftrag gestartet hat, und **Wartezeit**. Klappe **Schritte** auf, um die ausgeführte Phase, ihre Dauer, den Motor und das Modell zu sehen. Falls vorhanden, zeigt **Qualitätsprobleme** die Befunde aus der Selbstprüfung, der unabhängigen Prüfung und ihrer letzten Runde.

Öffne nach Auftragsende **Lieferbericht**. Lies **Änderungen**, **Prüfungen**, **Prüfergebnisse**, **Nicht abgeglichen** und **Deine Entscheidung**. Hat ein abgeschlossener Auftrag eine fehlgeschlagene Prüfung, steht diese zuerst. Wenn der Auftrag Commits erzeugt hat, sieh nach, wo sie gelandet sind. Konnte der Rechner sie nicht pushen, nennt der Bericht den lokalen Branch, den Commit, den Grund und einen ausführbaren Befehl. Ein reiner Berichtsauftrag kann seine Antwort ohne Commit liefern.

Öffne **Verbrauch** und klappe **Nach Runde** für die Tokenzahlen und tatsächlich verwendeten Modelle auf. Die Nutzung wird nach Anbieter, Konto und Modell erfasst. Die Summen der Lieferung beziehen sich auf die letzte Übernahme durch einen Rechner. Die Wartezeit wird getrennt von der Laufzeit erfasst.

## Einen Auftrag pausieren, ändern, stoppen oder fortsetzen

- Wähle bei einem wartenden Auftrag **Pausieren**, damit Rechner ihn nicht übernehmen, und dann **Fortsetzen**, wenn er wieder laufen kann. Wähle **Jetzt starten**, um einen wartenden Auftrag an den Anfang zu verschieben. Ist ein Platz belegt, kannst du weiter warten oder einen laufenden Auftrag ausdrücklich stoppen, um den Platz freizugeben.
- Um einen offenen Auftrag zu ändern, wähle am Auftrag **Zum Chat**. Dadurch wird seine Nummer eingefügt. Ergänze deine neuen Anforderungen und sende die Nachricht. Wenn der Leiter eine Änderung vorschlägt, wähle **Ja, Ändern**. Bei einem wartenden Auftrag wird die Aufgabenbeschreibung direkt ersetzt. Bei einem laufenden Auftrag endet der Versuch und der Auftrag kommt unter derselben Nummer erneut in die Warteschlange.
- Um einen Auftrag zu beenden, wähle **Stoppen** und bestätige. Ein ausdrücklich gestoppter Auftrag braucht deine Anweisung, um weiterzulaufen. Hat ein beendeter Auftrag einen gespeicherten Fortsetzungspunkt und verwendbare Arbeit, öffne ⋯ und wähle **Fortsetzen**. Er nutzt dieselbe Auftragsnummer und die erhaltene Arbeitskopie oder den gepushten Branch. Wenn du vor der Fortsetzung die Anforderungen änderst, beginnt er von vorn.
- Wähle **Erneut ausführen**, um einen neuen Auftrag mit dem ursprünglichen Ablauf, der Aufgabenbeschreibung, dem Repository und den Optionen einzureihen. Er erhält eine neue Nummer und der frühere Auftrag bleibt lesbar. Nutze dies, wenn **Fortsetzen** fehlt. **Löschen** entfernt den Eintrag eines beendeten Auftrags nach Bestätigung dauerhaft.

## Wenn es nicht funktioniert

- Ist die Auftragsverteilung für das ganze Team pausiert, wähle **Verteilung fortsetzen**, damit Rechner neue Aufträge übernehmen. Hat das Team oder dein Konto sein Limit für parallele Ausführungen erreicht, startet der Auftrag, sobald ein Platz frei wird. [Auftragsverteilung des Teams](teams.md)
- Wartet ein Auftrag auf deine Antwort, kannst du auch nach den ersten fünf Minuten noch antworten. Nach fünf Minuten gibt der Rechner den Platz frei. Sobald du antwortest, setzt derselbe Rechner den Auftrag fort, wenn er frei ist.
- Braucht ein Auftrag einen Schreiber oder Prüfer, wähle **Zu den Konten**. Ein Rechner muss die Konten für den gesamten Auftrag haben. Wenn alle infrage kommenden Rechner abgelehnt haben, schlägt der Auftrag fehl und seine Hinweise nennen die Gründe. Wartet er wegen Kontingent oder Tempo, prüfe die geschätzte Zeit. Die Arbeit geht weiter, sobald wieder Kontingent oder Kapazität verfügbar ist. [Motorkonten und Tempo](engine-accounts-and-pacing.md)
- Verliert ein Rechner die Verbindung, kann er bei der Wiederverbindung fortfahren. Nach 30 Minuten ohne Verlängerung seines Anspruchs kann ein anderer Rechner des Teams den Auftrag übernehmen und von vorn anfangen. Drei Verbindungsabbrüche beim selben Auftrag beenden ihn mit **Fehler**. Prüfe den Rechner, bevor du fortsetzt oder neu startest. [Rechner prüfen](machines.md)
- Nach einem behebbaren Systemfehler kann ein Auftrag insgesamt bis zu 10-mal automatisch fortgesetzt werden. Bleibt er beendet, lies den letzten Bericht, behebe die Ursache und wähle **Fortsetzen**, falls verfügbar.
