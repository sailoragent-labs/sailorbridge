[← SailorBridge](README.md)

# Motorkonten und Tempo

Deine Agents verwenden Motorkonten, die auf deinen Rechnern angemeldet sind. Du kannst sehen, welche Konten ein Team nutzen kann, wie viel Kontingent übrig ist und wann die Arbeit weitergeht. Dein SailorBridge-Tarif legt fest, wie viele Agents gleichzeitig laufen können. Modellzugriff und Kontingente kommen vom Anbieter des Motors.

## Ein Konto finden oder hinzufügen

1. Melde dich bei Claude Code oder Codex auf dem Rechner an, auf dem der Motor laufen soll. Führe `sail account list` aus. Eine Standardanmeldung wird automatisch erkannt. Ihr Name besteht in der Regel aus dem Motornamen, gefolgt von `@` und dem Rechnernamen.
2. Für eine weitere Anmeldung melde dich beim Motor in einem separaten Kontoverzeichnis an. Führe `sail account add <name> <directory>` mit diesem Verzeichnis und einem auf diesem Rechner eindeutigen Namen mit 1–64 Zeichen ohne Leerzeichen oder Schrägstriche aus. Liegt deine zweite Anmeldung zum Beispiel am folgenden Ort, führe `sail account add work "$HOME/codex-work"` aus. Die nächste Kontingentabfrage erkennt das Konto ohne Neustart.
3. Öffne **Ressourcen** und dann **Konten**. Wähle das Konto, um seine Rechner, das Kontingent und die verfügbaren Modelle zu sehen. Konten, die auf verschiedenen Rechnern unter demselben Namen vom selben Motor gemeldet werden, erscheinen in einer Zeile. Anmeldeverzeichnis, E-Mail-Adresse und Zugangsdaten bleiben auf dem Rechner.

Codex verwendet eine Anmeldung per Abonnement. Claude Code verwendet eine Anmeldung per Abonnement oder einen API-Schlüssel. Für Gemini CLI, Copilot CLI, OpenCode, Qwen Code und Pi stehen nur Kontoregistrierung und lokale Prüfungen zur Verfügung. Von diesen fünf erkennen Gemini CLI und OpenCode separate benannte Verzeichnisse.

## Einen Claude-kompatiblen Endpunkt verwenden

Richte für einen Anbieter wie DeepSeek oder GLM ein separates Claude-Code-Kontoverzeichnis auf deinem Rechner ein. Setze in seiner Datei `settings.json` die Basis-URL des Anbieters unter `env.ANTHROPIC_BASE_URL` und seine Zugangsdaten unter `env.ANTHROPIC_API_KEY` oder `env.ANTHROPIC_AUTH_TOKEN`. Setze `ANTHROPIC_MODEL` im selben Objekt `env` auf den Modellnamen des Anbieters. Die Familien Opus, Sonnet und Haiku kannst du mit `ANTHROPIC_DEFAULT_OPUS_MODEL`, `ANTHROPIC_DEFAULT_SONNET_MODEL` und `ANTHROPIC_DEFAULT_HAIKU_MODEL` getrennt zuordnen.

Führe dort `sail account add <name> <directory>` mit dem gewählten Namen und Pfad aus. Das Konto läuft über Claude Code. Öffne **Verfügbare Modelle**, um die aus dem Verzeichnis gelesenen Modellnamen zu sehen. Endpunktmodelle verwenden diese Zuordnungen und bieten keine Einstellung für den Aufwand. Die Auftragsdetails zeigen das tatsächlich verwendete Modell.

## Ein Konto für GLM, DeepSeek oder Kimi aus einer Vorlage einrichten

`sail account create` schreibt eine lokale Claude-Code-Einstellungsdatei mit dem Endpunkt des Anbieters, vorgeschlagenen Modellen für die hohe, mittlere und niedrige Stufe und einem Platzhalter für den Schlüssel. Der Befehl fragt deinen Schlüssel weder ab noch liest oder sendet er ihn. Er registriert das Konto auch nicht.

Führe zum Einrichten von GLM den folgenden Befehl auf dem Rechner aus, auf dem du das Konto nutzen willst.

```sh
sail account create glm
```

Der Befehl gibt drei Zeilen aus. Dabei steht `~` für dein Benutzerverzeichnis.

```text
Modellvorschlag (Opus/Fable, Sonnet, Haiku/Subagent): glm-5.3, glm-5.2, glm-5.3-flash.
Drei verschiedene Modell-IDs. Sonnet ist die vorgeschlagene mittlere Stufe.
In ~/.sailorbridge/account-templates/glm/settings.json den Platzhalter durch den eigenen API-Schlüssel ersetzen und dann sail account add <name> ~/.sailorbridge/account-templates/glm ausführen.
```

Die erzeugte Datei `settings.json` enthält diese Vorlage.

```json
{
  "env": {
    "ANTHROPIC_AUTH_TOKEN": "REPLACE_WITH_YOUR_API_KEY",
    "ANTHROPIC_BASE_URL": "https://api.z.ai/api/anthropic",
    "ANTHROPIC_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "glm-5.3",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "glm-5.2",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "glm-5.3-flash",
    "ANTHROPIC_DEFAULT_FABLE_MODEL": "glm-5.3",
    "CLAUDE_CODE_SUBAGENT_MODEL": "glm-5.3-flash"
  }
}
```

Öffne die Datei in einem Texteditor wie `nano`.

```sh
nano ~/.sailorbridge/account-templates/glm/settings.json
```

Ersetze `REPLACE_WITH_YOUR_API_KEY` durch deinen eigenen GLM-Schlüssel, behalte die Anführungszeichen und speichere die Datei. Registriere das Verzeichnis unter einem Namen deiner Wahl. In diesem Beispiel heißt es `glm`. Der Name muss auf diesem Rechner eindeutig und 1–64 Zeichen lang sein und darf keine Leerraumzeichen oder `/` enthalten.

```sh
sail account add glm ~/.sailorbridge/account-templates/glm
sail account list
```

Suche in der Terminalliste nach `glm`. Sobald der Rechner das Konto meldet, öffne in der App **Ressourcen** und dann **Konten**. Wähle `glm`, um seine **Verfügbare Modelle** zu sehen.

Beginne für DeepSeek oder Kimi mit dem Befehl für deinen Anbieter. Öffne die Datei `settings.json` am ausgegebenen Pfad und ersetze den Platzhalter durch den Schlüssel deines Anbieters. Verwende den ausgegebenen Befehl `sail account add` mit deinem gewählten Namen und prüfe dann `sail account list`.

| Vorlagenbefehl | Endpunkt in der Datei | Ausgegebene Modellvorschläge |
| --- | --- | --- |
| `sail account create deepseek` | `https://api.deepseek.com/anthropic` | Die hohe Stufe verwendet `deepseek-v4-pro`. Die mittlere und die niedrige Stufe verwenden beide `deepseek-flash`. |
| `sail account create kimi` | `https://api.kimi.com/coding/` | Verwende einen Schlüssel für den Kimi Coding Plan. Alle drei Stufen verwenden `k3.1-pro[1m]`. |

MiniMax verlangt `--region international` oder `--region china`. GLM, DeepSeek und Kimi lehnen `--region` ab.

## Kontingent ablesen und etwas für dich reservieren

Öffne das Konto unter **Konten**. Prüfe **Kontingent**, **Reset** und **Gemessen** gemeinsam. Eine Abfrage eines Abonnements kann ein Fünf-Stunden-Fenster, ein Wochenfenster oder ein Wochenkontingent für ein bestimmtes Modell anzeigen. Codex meldet seinen regulären Wochenpool. Die Kontingentabfrage verbraucht keine Modell-Tokens. Schlägt eine neue Abfrage fehl, kann ein bis zu einer Stunde alter erfolgreicher Wert angezeigt und als alt gekennzeichnet werden. Fehlt ein Wert, wird der Grund angegeben. Das Konto kann trotzdem für Aufträge infrage kommen.

- **Nutzbar** steuert neue Zuweisungen an dieses Konto in all deinen Teams. Beim Ausschalten kann laufende Arbeit zu Ende gehen.
- **Reserveschwelle** reserviert einen Prozentsatz für dich. Stelle ihn von 0% bis 100% in Schritten von 5 ein. Bleibt in einem Fenster von mehr als einem Tag höchstens dieser Prozentsatz übrig, verwenden weder Worker noch der **Leiter** das Konto weiter. Kurze Fenster nutzen ihr volles Kontingent.
- Wird ein Konto nach Ausgaben gemessen, setze **Monatslimit** auf den Höchstbetrag, den dieser Rechner in einem Kalendermonat verbrauchen darf. Das gilt zum Beispiel für DeepSeek. GLM liefert einen eigenen Kontingentwert. Ist das Limit erreicht, wartet neue Arbeit bis Mitternacht UTC am ersten Tag des Folgemonats, sofern du das Limit nicht erhöhst. Ein laufender Schritt kann oberhalb des Limits enden. Registrierst du dasselbe Konto auf mehreren Rechnern, misst jeder seine eigenen Ausgaben. Bei **Kosten nicht verfügbar** siehst du die Tokenzahl und das Limit greift nicht.
- Unter **Reset-Guthaben** erscheinen die Guthaben, die Claude oder Codex meldet. Öffne ein Guthaben, prüfe, was es zurücksetzt und wann es verfällt, wähle dann **Einlösen** und bestätige. **Reset einlösen** in der Kontoliste verwendet das passende Guthaben, das zuerst verfällt. Der Rechner mit dem Konto führt das Zurücksetzen aus. Prüfe das Ergebnis, bevor du ein weiteres Guthaben einlöst.

## Konten und Modelle für ein Team auswählen

Öffne **Kontenliste** im Teamchat-Menü. Konten auf den Rechnern des Teams sind standardmäßig enthalten. Setze **Rolle** auf **Beides**, **Nur schreiben** oder **Nur prüfen**, um festzulegen, welche Worker-Schritte das Konto verwenden dürfen. Verwende **Nur Leiter**, um das Konto für den Chat in diesem Team zu reservieren. **Aus Team entfernen** und **Konto zum Team hinzufügen** ändern seine Verfügbarkeit für dieses Team.

Öffne unter **Teamdetails** die Einstellungen für die Auftragsverteilung. Wähle unter **Leiter-Modell** ein nutzbares Konto auf einem Teamrechner, dann eines seiner erkannten Modelle und, falls angeboten, eine Aufwandsstufe. Die Wahl eines Kontos auf einem anderen Rechner verlegt den **Leiter** für die nächste Nachricht dorthin. Wenn das gewählte Konto nicht laufen kann, nennt die Antwort Ausweichmotor und Modell.

Lege für Worker in den Modelleinstellungen des Teams je Schwierigkeitsstufe und Motor bevorzugtes Modell und Aufwand fest. Die Schreib- und Prüfoptionen eines Ablaufs bestimmen den Motor. Bei automatischer Prüfung meidet der Prüfer nach Möglichkeit die tatsächlich verwendete Modellfamilie des Schreibers. Verlangt ein Ablauf einen Motor, für den das Team in dieser Rolle kein Konto hat, kann der Auftrag für diese Ausführung die automatische Auswahl nutzen. Die Auftragsdetails erklären die Änderung.

Ein Auftrag braucht einen Rechner, der alle Schritte ausführen kann. Dort nutzt jeder Schritt ein nutzbares Konto, das für seinen Motor und seine Rolle zugelassen ist. Unter den geeigneten Konten hat eine Anmeldung, die erneuert werden muss, Vorrang. Danach folgen Konten, deren Kontingent innerhalb eines Tages zurückgesetzt wird, das früheste zuerst. Bei späterem Zurücksetzen zählen nutzbares Kontingent, Tarifkapazität und verbleibende Zeit. Konten ohne Messwert kommen zuletzt. Eine Nachprüfung oder erste Prüfung von höchstens 120 geänderten Zeilen bevorzugt einen kleineren Tarif mit freiem Kontingent.

## Das Tempo neuer Arbeit einstellen

Öffne **Ressourcen** und dann **Tempomodus**. Die Standardeinstellung **Nach Kontingent** verteilt Arbeit über das Kontingentfenster. Ein Konto ist dem vorgesehenen Tempo voraus, wenn der verbrauchte Prozentsatz um mehr als 100/7 Prozentpunkte (etwa 14,3) über dem Anteil der vergangenen Zeit liegt und noch mehr als ein Siebtel des Fensters übrig ist. Sind alle geeigneten Konten voraus, wartet der Rechner vor der Annahme eines neuen Auftrags. Ein laufender Auftrag kann weiterlaufen. Auch der Chat mit dem **Leiter** kann weitergehen.

Wähle **Unbegrenzt**, damit alle deine Teams neue Aufträge ohne Warten auf diese Tempogrenze annehmen können. Reserven und ausgeschöpfte Kontingentfenster gelten weiterhin. Ist ein Konto in einem deiner Teams für den **Leiter** ausgewählt und sind weniger als 10% eines kontoweiten Fensters übrig, lassen die Worker es für den Chat frei. Du kannst auf derselben Seite zu **Nach Kontingent** zurückwechseln.

## Wenn es nicht funktioniert

- Existiert die Vorlagendatei bereits, überschreibt der Befehl sie nicht und gibt ihren Pfad aus. Bearbeite diese Datei und registriere ihr Verzeichnis.
- Lehnt der Befehl ein Verzeichnis ab, prüfe den ausgegebenen Pfad. Das Verzeichnis muss deinem Benutzer gehören und Modus `0700` haben, damit nur du darauf zugreifen kannst. Führe den Vorlagenbefehl erneut aus, nachdem Besitzer und Berechtigungen stimmen.
- `sail uninstall` entfernt `~/.sailorbridge/` einschließlich dieser Einstellungsdateien. Bewahre deshalb eine Kopie deines Schlüssels an einem anderen Ort auf.
- Schlägt die Registrierung fehl, folge dem Anmeldebefehl, den das Terminal für dein Verzeichnis ausgibt. Das Verzeichnis muss genau einem Motor zugeordnet sein. Prüfe den Namen mit `sail account list`. Um eine Registrierung zu entfernen oder eine Standardanmeldung zu ignorieren, führe `sail account remove <name>` aus. Die lokalen Zugangsdaten bleiben erhalten. Um eine Standardanmeldung wieder zu erkennen, führe `sail account restore claude` oder `sail account restore codex` aus oder öffne **Ignorierte Anmeldungen** des Rechners und wähle **Wiederherstellen**.
- Melde dich bei **Anmeldung abgelaufen** erneut auf dem genannten Rechner an. Bei **Anmeldung erneuern** versucht der Rechner, die Anmeldung zu erneuern. Prüfe bei **Netzwerk nicht verfügbar** die Verbindung dieses Rechners. Ist der Anbieter nicht verfügbar oder begrenzt er die Anfragen, folgt nach einer Pause ein neuer Versuch. Zeigt das Konto in der Modellauswahl **Modelle Noch Nicht Gelesen**, warte auf eine Abfrage oder wähle ein Konto mit einem erkannten Modell.
- Kann ein Team das Konto seines **Leiter** nicht entfernen, wähle zuerst ein anderes Konto unter **Leiter-Modell**. Fehlt einem Auftrag ein Schreiber oder Prüfer, wähle in seinen Details **Zu den Konten** und aktiviere die fehlende Rolle auf einem Rechner, der den ganzen Auftrag ausführen kann.
- Öffne **Auftragsliste** und lies **Warum er nicht läuft**. Bei einer Wartezeit wegen des Tempos erscheint eine Zeitschätzung. Du kannst warten oder **Auf unbegrenzt wechseln** für alle Teams bestätigen. Ein Auftrag, der die nutzbaren Konten ausgeschöpft hat, wartet auf demselben Rechner und prüft zur angezeigten Zeit erneut. Eine Anmeldung oder neues Kontingent lässt ihn automatisch weiterlaufen.
