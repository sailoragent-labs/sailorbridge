[← SailorBridge](README.md)

# Team-Gedächtnis

Das Team-Gedächtnis bewahrt Entscheidungen, Konventionen und Korrekturen auf, die dein **Leiter** und die Worker bei späteren Aufträgen nutzen können. Jeder Eintrag hat einen Titel, einen Inhalt, eine Quelle und eine Nummer wie `#6`. Ein Eintrag gehört zu einem Team. Andere Teams und Freunde können ihn nicht einsehen.

## Etwas zum Merken festhalten

Sag im Teamchat, was sich das Team merken soll und wann es gilt. Zum Beispiel „Merke dir, dass Installationsbeispiele in die Einrichtungsanleitung gehören. Nutze das beim Ändern eines Installationsbefehls.“ Der **Leiter** sagt dir, was er gespeichert hat. Öffne im Teamchat **Weitere Aktionen** und wähle **Team-Gedächtnis**, um den Eintrag zu sehen. Öffne seinen Titel, um den gesamten Text und die Person zu sehen, die ihn zuletzt geändert hat.

## Einen Eintrag finden und im Chat nutzen

Öffne **Suchen** unter **Team-Gedächtnis**. Gib Wörter aus dem Titel oder Inhalt ein. Bei einem Texttreffer müssen alle Wörter übereinstimmen. Auf der ersten Seite können auch bis zu drei Einträge mit ähnlicher Bedeutung erscheinen. In der normalen Liste stehen angeheftete Einträge oben.

Wenn du die Nummer kennst, suche nach `#6`, um nur Eintrag 6 zu finden. Die Suche nach `6` findet auch Texttreffer. Öffne den Eintrag und wähle **Zum Chat**. Im Eingabefeld steht jetzt `/memory #6`. Ergänze eine Frage oder Korrektur und sende sie ab.

## Einträge bearbeiten, anheften, sperren oder löschen

- Öffne den Eintrag, ändere **Inhalt** und wähle **Speichern**. **History** zeigt die letzten 10 Versionen. Prüfe für veränderliche Fakten **Observed** und **Expires**. Ein Eintrag mit **Expired** bleibt lesbar. Prüfe, ob sein Inhalt noch gilt.
- Aktiviere **Angeheftet**, um eine Anweisung in die Informationen für den **Leiter** und die Worker aufzunehmen. Der Eintrag zeigt an, wie viel Platz das Team fürs Anheften nutzt. Alle angehefteten Titel und Inhalte zusammen dürfen bis zu 8 KiB belegen.
- Aktiviere **Gesperrt**, wenn nur du den Eintrag ändern oder löschen dürfen sollst. Ein nur angehefteter Eintrag bleibt für Agents bearbeitbar. Gesperrte Einträge kannst du im Browser bearbeiten.
- Wähle **Löschen** und bestätige, um einen Eintrag dauerhaft zu entfernen. Seine Nummer wird nicht erneut vergeben.

## Die Einträge des Teams aufräumen

Sende `/memory-tidy` im Teamchat. Der Auftrag prüft Einträge, markiert erhaltenswerte, führt verwandte zusammen und löscht solche ohne künftigen Nutzen. Öffne den **Lieferbericht**, um zu sehen, was der Auftrag erledigt hat und was noch deine Entscheidung braucht. Gesperrte Einträge bleiben erhalten, wenn der Auftrag vorschlägt, sie zu löschen oder zusammenzuführen.

Das automatische Aufräumen läuft höchstens einmal pro Team innerhalb eines gleitenden Zeitraums von 24 Stunden, wenn Einträge zu prüfen sind. Soll es nur auf Anfrage oder nach Zeitplan laufen, öffne **Team-Abläufe**, wähle `memory-tidy` und deaktiviere **Automatisch aufräumen**.

## Wenn es nicht funktioniert

- Wenn das Anheften über 8 KiB hinausginge, wird es abgelehnt. Löse einen anderen Eintrag oder kürze den angehefteten Text und versuche es erneut.
- Hat jemand den Eintrag geändert, während du daran gearbeitet hast, erscheint der aktuelle Inhalt. Lies ihn, bevor du deine Korrektur erneut anwendest.
- Wenn zwei Änderungen denselben Titel verwenden, kann eine Korrektur desselben Autors direkt wirksam werden. Andernfalls kann eine höhere Bestätigungsstufe oder eine neuere Beobachtung auf derselben Stufe entscheiden. Brauchen die Änderungen eine Entscheidung, zeigt der Eintrag **Offener Konflikt** und behält den aktuellen Text. Öffne ihn, prüfe den Sachverhalt und speichere die richtige Formulierung. Bei einem gesperrten Eintrag entscheidest du.
- Meldet der **Leiter**, dass ein Eintrag nicht gespeichert wurde, wiederhole, was er sich merken soll. Wurde die Änderung eines Agents wegen der Sperre abgelehnt, ändere den Eintrag selbst unter **Team-Gedächtnis**.
