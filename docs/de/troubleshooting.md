[← SailorBridge](README.md)

# Fehlerbehebung

Beginne dort, wo die Arbeit aufgehört hat. Bei einer Anmeldung oder Zahlung lies die Meldung auf der betreffenden Seite. Bei einem Rechnerproblem prüfe das Terminal auf diesem Rechner. Öffne bei einem Auftrag die **Auftragsliste**, wähle ihn aus und lies **Warum er nicht läuft**. Dort steht, ob der Auftrag eine Aktion von dir braucht oder von selbst weiterläuft.

## Wieder Zugang zu deinem Konto bekommen

| Anzeige | Vorgehen |
| --- | --- |
| Deine Kapitän-ID ist vergeben oder die Registrierung ist für heute voll | Versuche es mit einer anderen verfügbaren ID. Ist das Tageslimit für kostenlose Registrierungen erreicht, versuche es morgen. Verwende für eine bezahlte ID den ursprünglichen **Einlöse-Link**, um die Registrierung abzuschließen. |
| **Bestätige, dass du es bist** nach der Passworteingabe | Nutze deine Authenticator-App, führe `sail confirm` auf einem gekoppelten Rechner aus und gib den Code ein oder bestätige die angezeigte Zahl in einem bekannten Browser, falls angeboten. Verwende die neueste Anmeldeanfrage. Läuft sie ab, melde dich erneut an. |
| Zu viele Anmeldefehler oder erneut verwendeter Authenticator-Code | Nach 5 Fehlern in 15 Minuten dauert die Standardsperre 15 Minuten. Warte die angezeigte Zeit ab. Wurde der Authenticator-Code bereits verwendet, warte auf den nächsten. |
| Du hast dein Passwort vergessen oder der Wiederherstellungscode ist abgelaufen | Führe `sail recover` im Terminal eines gekoppelten Rechners aus. Wähle **Passwort vergessen?** und gib die Kapitän-ID und den 8-stelligen Code aus der Ausgabe ein. Der Code gilt 10 Minuten und funktioniert einmal. Ein neuer Code vom selben Rechner ersetzt den alten. Wenn die Zugangsdaten des Rechners abgelehnt werden, versuche es mit einem anderen gekoppelten Rechner. Ohne einen verwendbaren gekoppelten Rechner musst du eine neue ID registrieren. |
| **Kontowiederherstellung wartet auf Wirksamkeit** | Bei einem vor weniger als 72 Stunden gekoppelten Rechner musst du 72 Stunden warten. Das gilt auch nach einer Reparatur, die seine Zugangsdaten ersetzt hat. Bei einer älteren Kopplung und seit mindestens 72 Stunden aktiver Bestätigung in zwei Schritten brauchst du den Authenticator-Code zur sofortigen Wiederherstellung. Ohne diesen Code stelle den Antrag mit 72 Stunden Wartezeit. Warte bis zum angezeigten Zeitpunkt. Wenn der Antrag nicht von dir stammt, wähle **Diese Wiederherstellung abbrechen** auf einem angemeldeten Gerät. |

## Einen Rechner oder ein Team zum Laufen bringen

- Bricht die Installation ab, weil Git fehlt, installiere Git und starte den Befehl von **Neuen Rechner koppeln** erneut. Ist Claude Code oder Codex abgemeldet, kannst du die Kopplung abschließen. Führe `claude login` oder `codex login` auf dem Rechner aus, bevor du das Team um Arbeit bittest.
- Läuft der Kopplungscode ab, hole mit `sail login` einen neuen. Gib ihn unter **Neuen Rechner koppeln** ein, wähle **Koppeln** und vergleiche Rechnernamen und **Schlüssel-Code** mit der Terminalanzeige, bevor du **Rechner genehmigen** wählst. Stimmen die Codes nicht überein, brich die Kopplung ab und beginne neu. Warte nach der Genehmigung, bis der Rechner verbunden ist.
- Hat sich der Rechner nach 10 Minuten noch nicht verbunden, führe `sail host status` aus. Der Befehl zeigt Dienststatus und Logpfad. Führe an derselben Adresse `sail login` aus, um den Dienst wiederherzustellen. Wenn `origin_mismatch` erscheint und du die Adresse wechseln willst, entfernt `sail uninstall` die lokalen SailorBridge-Daten einschließlich Arbeitskopien der Aufträge. Führe dann den Installationsbefehl von **Rechner** in der gewünschten App aus und kopple neu.
- Scheitert ein Update, öffne den Rechner unter **Rechner** und folge dem angezeigten Grund und Reparaturbefehl. Bei einem Downloadfehler versuche es später mit `sail upgrade` erneut. Bei einem Schreibfehler prüfe den Speicherplatz und verwende das Konto, das `sail` installiert hat.
- Verlangt die Teamerstellung einen Rechner, kopple einen und warte auf **Online**. Kannst du den letzten Rechner eines Teams nicht entfernen, nutze zuerst **Maschine hinzufügen**. Lässt sich das Teamverzeichnis nicht anlegen, wähle **Verzeichnis in den Teameinstellungen ändern**. Nutze einen absoluten Verzeichnispfad auf dem Rechner, auf dem der Fehler auftrat. Eine Datei an dieser Stelle, fehlende Schreibrechte oder ein schreibgeschützter Datenträger können das Anlegen verhindern. [Rechner](machines.md) · [Teams](teams.md)

## Eine Antwort im Chat bekommen

- Ist der Rechner des **Leiter** offline, speichert der Teamchat deine Nachricht und liefert sie bei Wiederverbindung aus. Hat das Team keinen verwendbaren Rechner, füge einen hinzu und sende die Nachricht erneut.
- Braucht der Motor eine Anmeldung, melde dich auf dem genannten Rechner an. Ist das Kontingent aller für den **Leiter** verwendbaren Konten erschöpft, sende die Nachricht nach dem angezeigten Rücksetzzeitpunkt erneut. Wird ein Modell abgelehnt, befolge die Update-Anweisung des Motors und versuche es erneut oder wähle ein verfügbares Konto und Modell. [Motorkonten und Tempo](engine-accounts-and-pacing.md)
- Wenn deine Nachricht statt an den **Leiter** an eine Frage ging, beantworte die offene Frage oder wähle **Stoppen** auf ihrer Karte. Sende dann die Nachricht. Wurde eine Bestätigungskarte ersetzt oder bereits beantwortet, prüfe vor dem Handeln die neueste Karte oder den Auftrag.
- Wird eine Datei abgelehnt, sende im Teamchat höchstens 4 Anhänge pro Nachricht mit jeweils bis zu 5 MiB. Unterstützt werden PNG, JPEG, WebP, PDF, Klartext und Markdown. Wähle einen nicht verfügbaren Anhang erneut aus. Ein nicht gesendeter Upload verfällt nach 24 Stunden. Warte beim Kontolimit von 1 GiB, bis gesendete Dateien nach 30 Tagen verfallen und Platz frei wird. Teile zu große Nachrichten in Nachrichten mit höchstens 64 KiB auf.
- Behebe in einer Agent-Sitzung zuerst ein Anmelde- oder Kontingentproblem des Kontos und wähle dann **Fortsetzen**. Erreicht eine Sitzung zwischen Teams das Rundenlimit, kann der Empfänger um 10 oder 20 Runden verlängern oder **Unbegrenzte Runden** wählen. Wer die Sitzung gestartet hat, wartet auf den Empfänger. [Chat](chat.md)

## Herausfinden, warum ein Auftrag wartet

Öffne den Auftrag in der **Auftragsliste**. Lies **Warum er nicht läuft**, bevor du entscheidest, ob du etwas neu startest.

| Was den Auftrag aufhält | Vorgehen |
| --- | --- |
| Die Auftragsverteilung oder dieser Auftrag ist pausiert | Verwende **Verteilung fortsetzen** für das Team oder **Fortsetzen** für den einzelnen Auftrag. |
| Die Rechner sind beschäftigt, das Team hat sein Auftragslimit erreicht oder dein Tarif sein Agent-Limit | Die Arbeit startet, sobald ein Platz frei wird. Prüfe **Gleichzeitige Aufträge** für das Team oder **Parallel-Limit** unter **Abonnement** für dein Konto. |
| Die Aufgabe braucht einen Schreiber und einen Prüfer | Wähle **Zu den Konten**. Stelle sicher, dass auf einem Teamrechner die nötigen Konten für beide Schritte aktiv sind. Ein Schreiber auf einem Rechner und ein Prüfer auf einem anderen können denselben Auftrag nicht gemeinsam ausführen. |
| Der Rechner hat die Tempogrenze erreicht oder das Kontingent ausgeschöpft | Warte die geschätzte Zeit ab. Bei Wartezeit wegen des Tempos ändert **Auf unbegrenzt wechseln** das Tempo für alle deine Teams nach Bestätigung. Bei ausgeschöpftem Kontingent prüft der Auftrag erneut und läuft auf demselben Rechner weiter, sobald wieder Kontingent verfügbar ist. |
| Der Auftrag braucht eine Antwort oder einen vorausgesetzten Auftrag | Wähle **Antworten**, wenn die Frage für dich bestimmt ist. Nach 5 Minuten Wartezeit gibt der Auftrag seinen Platz frei. Nach deiner Antwort läuft er weiter, sobald sein ursprünglicher Rechner frei ist. Bei einer Voraussetzung öffne die angezeigte Auftragsnummer und prüfe das Ergebnis. |
| Ein Rechner hat den Auftrag abgelehnt oder meldet sich nicht mehr | Lies den Grund unter dem Auftrag. Ein anderer geeigneter Rechner kann einen abgelehnten Auftrag übernehmen. Haben alle Kandidaten abgelehnt, öffne **Notiz der Maschine**, um ihre Gründe zu sehen. Hat der ausführende Rechner die Verbindung verloren, kann er fortfahren, wenn er zuerst zurückkehrt. Nach 30 Minuten ohne Verlängerung kann ein anderer Rechner von vorn beginnen. |
| **Unvollständig** oder **Fehler** | Öffne **Lieferbericht** für den letzten Schritt, den Grund und die erhaltene Arbeit. Behebe das gemeldete Problem. Nutze **Fortsetzen**, falls angeboten, um denselben Auftrag mit der erhaltenen Arbeit fortzusetzen, oder **Erneut ausführen**, um neu zu beginnen. Ist ein Push gescheitert, nennt der Bericht Branch, Commit und Push-Befehl für die lokal erhaltene Arbeit. |

## Einen Befehl, Zeitplan oder Gedächtniseintrag korrigieren

- Meldet das Terminal „Führe diesen Befehl in einem Job oder einer Teamleiter-Sitzung aus.“ (`local_team_context_missing`), braucht der Befehl auch im Teamverzeichnis eine aktive Sitzung. Frage den **Leiter** im Teamchat oder öffne **Auftragsliste**, **Geplante Ereignisse** oder **Team-Gedächtnis**, um mit einem vorhandenen Eintrag zu arbeiten. [Befehle für nummerierte Einträge eines Teams](commands.md#mit-nummerierten-einträgen-eines-teams-arbeiten)
- Ist ein Slash-Befehl unbekannt, gib `/` ein, um aktivierte Abläufe zu sehen. Fehlt ein nummerierter Verweis, prüfe Team und Eintragstyp und schreibe `#` vor die Nummer im Chat. Meldet `sail exec`, dass das Ziel offline ist, wurde der Befehl nicht gestartet. Ging das Ergebnis *nach* dem Start verloren, prüfe vor einem erneuten Versuch den Zielrechner. [Befehle](commands.md)
- Wird ein geplantes Ereignis abgelehnt, wähle eine künftige Zeit für ein einmaliges Ereignis oder ein Intervall von 5–720 Minuten für eine Wiederholung. Ein Team kann bis zu 20 Ereignisse haben. Lösche ein nicht benötigtes Ereignis, um Platz zu schaffen. Ein beendetes einmaliges Ereignis musst du für eine Wiederholung neu erstellen. Verweist ein Ereignis auf einen deaktivierten Ablauf oder eine fehlende Nummer, korrigiere die Nachricht für die nächste Ausführung. [Abläufe und geplante Ereignisse](flows-and-scheduled-events.md)
- Wird eine Änderung am Gedächtnis abgelehnt, öffne **Team-Gedächtnis**. Dort kannst du einen gesperrten Eintrag ändern. Hat ihn zuvor jemand anderes geändert, lies vor dem Speichern den aktuellen Inhalt. Ist der Platz für angeheftete Einträge voll, löse oder kürze einen Eintrag, bevor du einen weiteren anheftest. [Team-Gedächtnis](team-memory.md)

## Eine noch nicht abgeschlossene Zahlung prüfen

Wenn die Zahlung aussteht, kehre zum ursprünglichen Kauf zurück und prüfe seinen Status, bevor du erneut zahlst. Bei **Zahlung fehlgeschlagen** für ein Abonnement öffnet **Zahlungsmethode Ändern und Rückstand Zahlen** den Bezahlvorgang für den offenen Betrag. [Tarife und Abrechnung](plans-and-billing.md)

## Wenn es nicht funktioniert

Besteht das Problem weiter, notiere die Schritte, die genaue Meldung, das erwartete Ergebnis und wo es passiert ist. Gib Version, Betriebssystem des Rechners und Motor an, wenn du sie kennst. Nutze bei einem Konto- oder Zahlungsproblem den privaten Kontakt in der README. Nutze bei einem Sicherheitsproblem den dortigen privaten Link. Halte Zugangsdaten, Kopplungscodes, Zahlungsdaten und privaten Quellcode aus öffentlichen Meldungen heraus. [Ein Problem melden](README.md#ein-problem-melden)
