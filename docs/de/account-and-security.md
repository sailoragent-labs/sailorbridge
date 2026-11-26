[← SailorBridge](README.md)

# Konto und Sicherheit

Deine numerische **Kapitän-ID** ist dein Anmeldename. Sie bleibt deinem Konto zugeordnet, auch wenn du deinen Spitznamen, dein Passwort oder deinen Browser wechselst. Kopple einen Rechner, den du kontrollierst, solange du dich noch anmelden kannst. Wenn du dein Passwort vergisst, brauchst du einen gekoppelten Rechner.

## Konto erstellen

1. Öffne die [App](https://app.sailorbridge.com) und wähle **Registrieren**. Gib deine gewünschte 3- bis 11-stellige Nummer ein. Wenn **Bereits beansprucht** erscheint, ändere die Nummer und prüfe eine andere.
2. Prüfe die Anzeige für diese Nummer. Normale 6–8-stellige IDs und alle 9–11-stelligen IDs sind kostenlos. Kürzere IDs und besondere Zahlenmuster mit bis zu 8 Stellen kosten einmalig Geld. Speichere beim Bezahlen einer Nummer den **Einlöse-Link**, damit du die Registrierung auf einem anderen Gerät abschließen kannst. [Preise](https://www.sailorbridge.com/#pricing)
3. Lege dein Passwort fest und bestätige es. Du kannst einen vorgegebenen Avatar wählen oder deinen Anfangsbuchstaben behalten. Bestätige dein Alter, akzeptiere die **Nutzungsbedingungen** und wähle dann **Registrieren**. Die App meldet dich an. [Ersten Rechner koppeln](machines.md)

## Anmelden und einen neuen Browser bestätigen

Gib deine **Kapitän-ID** ein und wähle **Weiter**. Gib dann dein **Passwort** ein und wähle **Melden Sie sich an**. Wenn ein Rechner gekoppelt ist, verlangt SailorBridge in einem neuen Browser automatisch eine Bestätigung. Bei ausgeschalteter Bestätigung in zwei Schritten genügt in einem bekannten Browser das Passwort. Ohne gekoppelten Rechner und ohne Bestätigung in zwei Schritten genügt es auch in einem neuen Browser. Wenn du die optionale **Bestätigung in zwei Schritten** aktivierst, ist bei jeder Anmeldung eine Bestätigung nötig, auch in bekannten Browsern.

Nutze unter **Bestätige, dass du es bist** eine der angebotenen Methoden.

- Gib unter **Authenticator-Code** den aktuellen Code deiner Authenticator-App ein.
- Führe für **Code vom Rechner** den Befehl `sail confirm` im Terminal eines gekoppelten Rechners aus. Gib den achtstelligen Code auf der Anmeldeseite ein.
- Für die **Bestätigung im Browser** öffnest du einen anderen bekannten Browser, in dem du bereits angemeldet bist. Tippe in der Abfrage auf die zweistellige Zahl von der Anmeldeseite. Bestätige nur eine Anmeldung, die du selbst begonnen hast. Wähle andernfalls **Das war ich nicht**.

## Profil einrichten und die Anmeldung schützen

Öffne **Ich**. Du kannst einen **Spitzname** festlegen und einen **Avatar** aus der Galerie wählen. **Sprache** bestimmt die Anzeigesprache und die Sprache der Antworten ab dem nächsten Chatbeitrag oder Auftrag. Wähle unter **Antwortstil** die Option **Einsteiger** für mehr Erklärungen oder **Experte** für kürzere Antworten.

Öffne **Sicherheit** und dann **Bestätigung in zwei Schritten**. Wähle **Aktivieren**, bestätige dein Passwort und scanne den QR-Code mit deiner Authenticator-App. Gib den aktuellen Code ein und wähle **Bestätigen und aktivieren**. Zum Ausschalten wählst du **Bestätigung in zwei Schritten deaktivieren** und gibst dein Passwort und einen neuen Code ein.

Um dein Passwort zu ändern, fülle **Aktuelles Passwort**, **Neues Passwort** und **Bestätigen Sie das neue Passwort** unter **Sicherheit** aus. Gib einen Authenticator-Code ein, wenn die Bestätigung in zwei Schritten aktiv ist. Nach der Änderung bist du in diesem Browser angemeldet. Andere Sitzungen werden abgemeldet.

<a name="aktivitäten-und-geräteschlüssel-prüfen"></a>

## Aktivitäten und Geräte prüfen

Öffne **Ich**, dann **Sicherheit** und **Letzte Sicherheitsereignisse**. Die Liste umfasst die letzten 90 Tage. Nach einer erfolgreichen Anmeldung in einem neuen Browser wirst du gefragt, ob du es warst. Wähle **Das war ich** oder **Das war ich nicht**. Jeder Browser speichert seine Bestätigungen separat. Fehlgeschlagene Anmeldungen erscheinen ohne Bestätigungsaufforderung in der Liste.

Wenn du eine fremde Anmeldung siehst, ändere dein Passwort. Mit **Andere Sitzungen abmelden** meldest du andere Browser und Apps ab und bleibst hier angemeldet. Wenn du nur einen Rechner trennen willst, entferne ihn unter **Rechner**. **Alle Rechner widerrufen** trennt alle gekoppelten Rechner. Du musst sie erneut koppeln, bevor sie arbeiten oder einen Wiederherstellungscode ausgeben können. Du kannst auch einen einzelnen Sicherheitseintrag nach Bestätigung löschen. Andere Browser zeigen ihre eigenen Warnungen an, bis das Ereignis dort bestätigt wird.

Öffne unter **Sicherheit** die Seite **Geräte**. Dort siehst du deine Apps und gekoppelten Rechner. Wähle ein Gerät und dann **Entfernen**, damit das Gerät keine neuen Aktionen mehr autorisieren kann. Dadurch wird die App abgemeldet oder der Rechner getrennt. Wähle bei einem fehlenden Gerät **Verloren oder gestohlen**. SailorBridge akzeptiert dann auch keine Inhalte mehr, die dieses Gerät früher autorisiert hat.

## Vergessenes Passwort wiederherstellen

1. Führe `sail recover` im Terminal eines gekoppelten Rechners aus. Der Befehl gibt deine Kapitän-ID und einen achtstelligen Wiederherstellungscode aus, der 10 Minuten lang gültig ist und einmal verwendet werden kann. Ein neuer Code auf demselben Rechner ersetzt den ersten.
2. Wähle auf der Anmeldeseite **Passwort vergessen?**. Gib die ID und den **Wiederherstellungscode** aus dem Terminal ein. Prüfe den Rechnernamen und das Kopplungsdatum, bevor du dein neues Passwort eingibst.
3. Folge dem angezeigten Wiederherstellungsweg. Für das Alter der Kopplung zählt die letzte Kopplung oder Reparatur der Zugangsdaten.

| Rechner für die Wiederherstellung | Bestätigung in zwei Schritten | Was passiert |
| --- | --- | --- |
| Vor weniger als 72 Stunden gekoppelt | Beliebige Einstellung | Stelle einen Wiederherstellungsantrag mit 72 Stunden Wartezeit, auch wenn du einen Authenticator-Code hast. |
| Vor mindestens 72 Stunden gekoppelt | Aus oder seit weniger als 72 Stunden aktiv | Setze das Passwort sofort mit dem Wiederherstellungscode zurück. Dabei wird eine kürzlich aktivierte Bestätigung in zwei Schritten ausgeschaltet. |
| Vor mindestens 72 Stunden gekoppelt | Seit mindestens 72 Stunden aktiv | Gib einen Authenticator-Code ein, um das Passwort sofort zurückzusetzen und die Bestätigung in zwei Schritten beizubehalten. Ohne diesen Code stellst du einen Wiederherstellungsantrag mit 72 Stunden Wartezeit. |

Wenn du warten musst, wähle **Wiederherstellung mit 72 Stunden Wartezeit beantragen** und richte dich nach der Zeit auf der Wiederherstellungsseite. Angemeldete Geräte werden benachrichtigt. Auf einem davon kannst du **Diese Wiederherstellung abbrechen** wählen. Auch eine erfolgreiche Anmeldung bricht den Antrag ab. Sobald das Passwort zurückgesetzt ist, melde dich mit dem neuen Passwort an. Die Wiederherstellung mit Wartezeit setzt die Bestätigung in zwei Schritten zurück.

Prüfe nach der Wiederherstellung **Gekoppelt am** unter **Rechner** und entferne alle Rechner, die du nicht erkennst. Die Bestätigung in zwei Schritten kannst du unter **Sicherheit** wieder aktivieren.

## Abmelden oder Konto löschen

Wähle **Abmelden** unter **Ich**, um die Sitzung in diesem Browser zu beenden. Um das Konto zu schließen, wähle **Konto löschen**, prüfe die betroffenen Teams und Rechner und bestätige mit deinem Passwort sowie, falls aktiviert, einem Authenticator-Code. Die Löschung meldet deine Geräte ab, entzieht deinen Rechnern den Zugriff und kündigt dein Abonnement. Melde dich innerhalb von sieben Tagen an, um den Antrag rückgängig zu machen. In dieser Zeit lässt sich dein Passwort nicht wiederherstellen, weil die Rechner keinen Zugriff mehr haben. Nach Ablauf der Frist wird das Konto gelöscht und seine Nummer bleibt gesperrt.

## Wenn es nicht funktioniert

- Nach fünf fehlgeschlagenen Anmeldeversuchen innerhalb von 15 Minuten dauert die Standardsperre 15 Minuten. Warte die angezeigte Zeit ab. Einen Authenticator-Code kannst du einmal verwenden. Wenn du ihn gerade verwendet hast, warte auf den nächsten.
- Wenn die Browserbestätigung abgelaufen ist oder du auf die falsche Zahl getippt hast, starte die Anmeldung neu. Du kannst auch eine der angebotenen Methoden mit Code verwenden. Mit `sail confirm` erhältst du einen neuen Anmeldecode, mit `sail recover` einen neuen Wiederherstellungscode.
- Wenn ein Rechner keinen Wiederherstellungscode ausgeben kann, versuche es mit einem anderen gekoppelten Rechner deines Kontos. Wenn keiner gültige Zugangsdaten hat, lässt sich das Konto nicht wiederherstellen. Registriere eine neue ID.
