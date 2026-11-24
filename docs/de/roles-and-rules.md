[← SailorBridge](README.md)

# Rollen und Regeln

Jedes Team hat einen **Leiter**. Du sprichst mit ihm im Teamchat. Er beantwortet Fragen, führt kurze Befehle aus und übergibt längere Arbeiten an einen Ablauf. Ein Worker führt einen Schritt dieses Ablaufs auf einem Rechner des Teams aus. Dauerhafte Anweisungen für den Motor hinterlegst du im Projekt-Repository. Einen Rolleneditor und eine Regelbibliothek gibt es nicht.

## Dem Team passende Aufgaben geben

Öffne den **Chat** deines Teams. Frage „Auf welchem Branch sind wir?“ Der **Leiter** kann das Teamverzeichnis prüfen und im Chat antworten. Für eine kurze Prüfung auf einem anderen Rechner im Team gib `@` ein, wähle den Rechner und beschreibe, was geprüft werden soll. Du erhältst eine Zusammenfassung des Ergebnisses.

Wenn eine Arbeit geliefert und geprüft werden soll, schreibe etwa „Aktualisiere die Einrichtungsanleitung und lass sie prüfen.“ Wenn der **Leiter** einen Hintergrundablauf vorschlägt, lies die Aufgabe auf der Karte. Wähle **Ja, Machen**, um sie einzureihen, oder **Nicht So**, um zu erklären, was sich ändern soll. Öffne die **Auftragsliste**, um die Schritte der Worker zu verfolgen. Braucht ein Worker eine Entscheidung, prüft der **Leiter** zunächst, was das Team bereits weiß, und fragt dich im Chat, wenn er deine Antwort braucht.

## Dem Motor eine dauerhafte Anweisung geben

Hinterlege projektweite Anweisungen in `AGENTS.md` für Codex oder `CLAUDE.md` für Claude Code im Repository. Halte zum Beispiel fest, welcher Befehl vor der Übergabe einer Änderung auszuführen ist. Der Motor liest seine Anweisungsdatei, wenn er in diesem Repository arbeitet. Soll das Team sich etwas über mehrere Aufträge hinweg merken, kannst du es auch im Chat darum bitten. [Team-Gedächtnis](team-memory.md)

## Ein Gespräch nach einer Pause fortsetzen

Sende deine nächste Nachricht im selben Teamchat. Der **Leiter** kann nach einer langen Pause, einem Motorwechsel oder dem Wechsel auf einen anderen Rechner eine neue Motorsitzung beginnen. Er übernimmt die gespeicherte Zusammenfassung des Teams, die letzten Nachrichten, das Team-Gedächtnis und die offenen Aufträge. Wenn **Unterhaltung wird aufgeräumt…** angezeigt wird, kannst du trotzdem eine Nachricht senden. Der **Leiter** antwortet, sobald die Zusammenfassung fertig ist.

## Wenn es nicht funktioniert

- Fehlt ein früheres Detail, nenne in deiner nächsten Nachricht die Auftragsnummer, die Entscheidung oder die betreffende Datei. Eine neue Sitzung erhält die letzten 20 Nachrichten und, falls vorhanden, eine Zusammenfassung.
- Wenn eine falsche Anweisung aus einem früheren Gespräch weiterwirkt, wähle **Chat leeren**, prüfe den Teamnamen und bestätige. Frühere Nachrichten verschwinden aus der Chatansicht und die nächste Sitzung startet ohne die alte Zusammenfassung. Stammt die Anweisung aus einer Repository-Datei oder dem Team-Gedächtnis, korrigiere sie dort.
- Wenn dem **Leiter** die Zeit ausgeht, frage in kleineren Schritten nach oder sende die längere Aufgabe als Auftrag. [Befehle](commands.md)
