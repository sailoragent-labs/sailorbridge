[← SailorBridge](README.md)

# Teams

Ein Team gibt einem Projekt einen eigenen Chat mit dem **Leiter**, eine Auftragswarteschlange, ein Team-Gedächtnis und einen oder mehrere Rechner. Du kannst mehrere Teams besitzen und denselben Rechner in mehr als einem Team nutzen. Nur du kannst die Einstellungen deines Teams ansehen und ändern.

## Ein Team für dein Projekt erstellen

1. Kopple den Rechner, auf dem der Leiter laufen soll. Sobald **Online** erscheint, wähle auf der Kopplungsseite **Team Erstellen**. Du kannst auch unter **Teams** mit **Team erstellen** beginnen. [Einen Rechner koppeln](machines.md)
2. Gib einen **Teamname** ein und wähle den Rechner. Du kannst aus den Optionen für diesen Rechner einen **Avatar**, ein Leiterkonto, ein Modell und eine Aufwandsstufe auswählen oder die Voreinstellungen verwenden.
3. Gib unter **Projektverzeichnis** den absoluten Pfad auf dem ausgewählten Rechner ein. Er beginnt mit `/`. Arbeitest du bereits in einem Repository, verwende dessen lokales Verzeichnis. Möchtest du in einem bestehenden Remote-Repository arbeiten, klone es zuerst auf diesem Rechner und richte dort die Git-Zugangsdaten ein. SailorBridge erkennt den Hauptbranch des Repositorys.
4. Wähle ein **Ziel** und dann **Team erstellen**. Das Team listet den Rechner nun auf. Öffne den **Chat**, um mit dem Leiter zu sprechen. [Teamchat nutzen](chat.md)

Bei der ersten Verwendung des Pfads öffnet das Team den vorhandenen Ordner oder legt ihn an. In einem einfachen Ordner mit Dateien initialisiert es Git und erstellt einen ersten Snapshot. Wenn der Ordner direkt mehrere Git-Repositorys enthält, sag dem Leiter, welches du meinst. Jeder Auftrag arbeitet in einem Repository. Arbeiten über mehrere Repositorys werden in einzelne Aufträge aufgeteilt.

## Festlegen, wohin Änderungen gehen

Öffne dein Team unter **Teams**, um zu **Teamdetails** zu gelangen. Ändere dort **Projektverzeichnis** oder **Ziel**. Die Änderungen gelten ab dem nächsten Auftrag, den ein Rechner übernimmt.

| Ziel | Wo die Commits eines Auftrags liegen |
| --- | --- |
| **Auto-Merge** (Standard) | Der Rechner versucht, in den Hauptbranch des Remotes zu pushen, und zieht dann seinen lokalen Hauptbranch per Fast-Forward nach. Prüfe die Lieferung, wenn der Hauptbranch weitergelaufen ist oder das Remote eine Prüfung verlangt. Ist dort ein Auftragsbranch angegeben, merge diesen Branch auf dem Remote. |
| **Branch** | Jeder Auftrag pusht einen eigenen Branch `sb/<job>`, den du prüfen und mergen kannst. Andere Aufträge starten vom Hauptbranch des Projekts. |

Jeder Rechner verwendet das Git-Remote und die Zugangsdaten des Repositorys. Vor Beginn eines Auftrags ruft er den Hauptbranch des Remotes ab und zieht seine lokale Kopie nach Möglichkeit per Fast-Forward nach. Schlägt ein Push fehl, öffne den **Lieferbericht** des Auftrags. Dort stehen der Grund, der lokale Branch, der Commit und der Push-Befehl. [Lieferung eines Auftrags finden](jobs.md)

## Einen Rechner hinzufügen, verschieben oder entfernen

Öffne unter **Teamdetails** die **Maschinenliste** und wähle das Pluszeichen für **Maschine hinzufügen**. Wähle einen gekoppelten Rechner und dann **Wie der Teamordner** oder gib unter **Projektordner** einen eigenen absoluten Pfad ein. Du kannst diesen Pfad später ändern. Ein geeigneter Rechner mit freier Kapazität kann jetzt einen Auftrag aus derselben Warteschlange übernehmen.

Um einen Rechner aus diesem Team zu entfernen, wähle ihn aus und bestätige **Aus dem Team entfernen**. Er übernimmt keine neuen Aufträge aus dieser Warteschlange. Entfernst du den Rechner mit der Kennzeichnung **Hier läuft der Leiter** oder musterst ihn aus, übernimmt der am frühesten beigetretene verbleibende Rechner die Leitung. Der letzte Rechner eines Teams lässt sich nicht entfernen. Füge zuerst seinen Ersatz hinzu.

## Festlegen, wie das Team Aufträge übernimmt

Kehre zu **Teamdetails** zurück, um zu ändern, wie dieses Team arbeitet.

- Unter **Auftragseinstellungen** steuert **Verteilung** die Übernahme neuer Arbeit. Wähle **Pausiert**, um wartende Aufträge zurückzuhalten, während laufende weiterarbeiten. Wähle **Normal**, damit Rechner wieder wartende Aufträge übernehmen.
- **Gleichzeitige Aufträge** steht standardmäßig auf **Unbegrenzt**, sodass das Limit deines Kontos gilt. Wähle **Anzahl festlegen**, um die Zahl laufender Aufträge für dieses Team zu begrenzen. Eine Senkung wird wirksam, sobald laufende Aufträge enden.
- Wähle unter **Leiter-Modell** das Konto, dann das Modell und, falls angeboten, die Aufwandsstufe. Konten stehen mit ihrem Rechner in der Liste. Wählst du ein Konto auf einem anderen Rechner des Teams, wechselt der Leiter für die nächste Nachricht dorthin. Er verwendet dieselbe Gesprächszusammenfassung und dasselbe Team-Gedächtnis. Laufende Aufträge bleiben auf ihren Rechnern.
- Wähle für Worker je Schwierigkeitsstufe und Anbieter das bevorzugte Modell und, soweit verfügbar, den Aufwand. **Standard wiederherstellen** setzt die Auswahl auf die Voreinstellung des Teams zurück. In der **Kontenliste** kannst du ein Konto auf Schreiben, Prüfen oder den Leiter beschränken. [Motorkonten und Tempo](engine-accounts-and-pacing.md)

## Ein Team auflösen

Öffne **Teamdetails**, wähle **Team auflösen** und prüfe, wie viele Agent-Sitzungen enden. Gib dann zur Bestätigung den Teamnamen ein. Die Auflösung ist endgültig. Sie bricht offene Aufträge ab, löscht geplante Ereignisse und entfernt das Team aus deiner Liste und den Chat-Einstiegspunkten. Ausstehende Anfragen für Agent-Sitzungen und aktive Sitzungen enden. Alle Beteiligten behalten ihren Sitzungsverlauf. Die Rechner bleiben mit deinem Konto gekoppelt.

## Wenn es nicht funktioniert

- Wenn kein Rechner zur Auswahl steht, wähle beim Erstellen eines Teams **Maschine koppeln** oder beim Hinzufügen eines Rechners **Neue Maschine koppeln**. Wurde der Rechner ausgemustert, kopple ihn erneut, bevor du ihn hinzufügst.
- Meldet ein Auftrag oder Chat, dass das Verzeichnis nicht angelegt werden kann, prüfe den Pfad auf dem Rechner, der es verwenden wollte. Eine Datei an dieser Stelle, fehlende Schreibrechte oder ein schreibgeschützter Datenträger können das Anlegen verhindern. Wähle **Verzeichnis in den Teameinstellungen ändern** und gib ein beschreibbares Verzeichnis für diesen Rechner ein.
- Ist dein Leiterkonto oder -modell beim Erstellen nicht mehr verfügbar, wähle erneut aus der aktualisierten Liste. Wenn Aufträge nach dem Erstellen warten, lies in den Auftragsdetails **Warum er nicht läuft**, um zu sehen, ob die Auftragsverteilung, ein Limit oder ein Konto sie aufhält.
