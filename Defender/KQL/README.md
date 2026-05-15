# Microsoft Defender XDR – Advanced Hunting KQL Queries

Willkommen in diesem Bereich für **Microsoft Defender XDR Advanced Hunting Queries**.

Hier werden praxisnahe KQL-Abfragen bereitgestellt, die bei der Analyse von sicherheitsrelevanten Ereignissen in Microsoft 365 und Microsoft Defender XDR unterstützen. Der Fokus liegt auf nachvollziehbaren, wiederverwendbaren und gut kommentierten Queries für typische Fragestellungen aus Security Operations, Incident Response und Threat Hunting.

## Wofür sind diese Queries gedacht?

Die bereitgestellten Abfragen helfen dabei, sicherheitsrelevante Ereignisse schneller einzuordnen und technische Zusammenhänge sichtbar zu machen. Sie können beispielsweise genutzt werden, um verdächtige E-Mails, Benutzerinteraktionen, Dateiaktivitäten oder auffällige Aktivitäten in einer Microsoft 365 Umgebung zu untersuchen.

Ein typischer Anwendungsfall ist die Analyse einer verdächtigen E-Mail-Kampagne:

- Welche Benutzer haben eine verdächtige E-Mail erhalten?
- Wurde ein enthaltener Link angeklickt?
- Hat Microsoft Defender den Zugriff auf einen Link erlaubt oder blockiert?
- Wurden Anhänge erkannt und bewertet?
- Ist ein Anhang oder dessen Hashwert auf einem Endpoint aufgetreten?
- Welche Geräte oder Benutzer waren potenziell betroffen?

Die Queries sollen dabei helfen, aus vorhandenen Defender-XDR-Daten eine erste technische Bewertung abzuleiten und weitere Schritte für Analyse, Bewertung oder Incident Response vorzubereiten.

## Aktuelle Inhalte

Der Ordner enthält aktuell eine dokumentierte Query zur:

### E-Mail-, Link- und Attachment-Analyse

Diese Query korreliert Informationen aus mehreren Microsoft Defender XDR Datenquellen, um verdächtige oder schadhafte E-Mails genauer zu untersuchen.

Sie unterstützt unter anderem bei der Beantwortung folgender Fragen:

- Wurde eine verdächtige E-Mail zugestellt?
- An welche Empfänger wurde sie ausgeliefert?
- Enthielt die E-Mail Links oder Anhänge?
- Wurde ein Link angeklickt?
- Wurde ein Safe-Links-Warning möglicherweise übergangen?
- Welche Anhänge waren enthalten?
- Welche Hashwerte wurden zu den Anhängen ermittelt?
- Wurde ein Attachment-Hash auf einem Microsoft Defender for Endpoint Gerät gesehen?

## Voraussetzungen

Die Nutzbarkeit der Queries hängt davon ab, welche Microsoft Defender Dienste in der jeweiligen Umgebung lizenziert, aktiviert und mit Daten befüllt sind.

Je nach Query können unter anderem folgende Datenquellen relevant sein:

- Microsoft Defender XDR Advanced Hunting
- Microsoft Defender for Office 365
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Microsoft Entra ID Audit- und Sign-in-Daten

Nicht jede Query liefert in jeder Umgebung automatisch Ergebnisse. Fehlende Ergebnisse können z. B. durch nicht aktivierte Workloads, fehlende Lizenzen, eingeschränkte Datenretention oder nicht onboarded Endpoints verursacht werden.

## Nutzung

1. Gewünschte `.kql` Datei aus diesem Ordner öffnen.
2. Inhalt in **Microsoft Defender XDR > Hunting > Advanced hunting** kopieren.
3. Die Parameter im oberen Bereich der Query anpassen, z. B. Zeitraum, Absenderadresse, Domain oder weitere Filter.
4. Query ausführen.
5. Ergebnisse fachlich bewerten und bei Bedarf durch weitere Datenquellen ergänzen.

Die Queries sind bewusst kommentiert, damit nachvollziehbar bleibt, welche Datenquellen verwendet werden und wie die Ergebnisse zu interpretieren sind.

## Wichtige Hinweise zur Interpretation

Die Ergebnisse sollten immer im Kontext der jeweiligen Umgebung bewertet werden.

Beispiele:

- Ein erkannter Link-Klick zeigt eine registrierte Benutzerinteraktion, bedeutet aber nicht automatisch, dass ein Schaden entstanden ist.
- Ein blockierter Safe-Links-Klick kann darauf hinweisen, dass die Schutzmechanismen erfolgreich gegriffen haben.
- Ein beobachteter Attachment-Hash auf einem Endpoint zeigt, dass eine Datei mit diesem Hash auf dem Gerät aufgetreten ist.
- Ein Endpoint-Treffer beweist nicht automatisch, dass ein Benutzer den Anhang aktiv geöffnet hat.
- Keine Treffer bedeuten nicht automatisch, dass keine Interaktion stattgefunden hat. Mögliche Gründe sind z. B. fehlende Telemetrie, mobile Nutzung, nicht onboarded Geräte oder abgelaufene Datenretention.

Die Queries sind daher als technische Analysehilfe zu verstehen und sollten im Rahmen einer vollständigen Security-Bewertung mit weiteren Informationen kombiniert werden.

## Zielgruppe

Dieses Repository richtet sich an:

- Security Operations Teams
- Incident Response Teams
- Microsoft 365 Administratoren
- Defender XDR Administratoren
- IT-Sicherheitsverantwortliche
- Consultants und Architekten im Microsoft Security Umfeld
- Interessierte, die praxisnahe KQL-Beispiele für Microsoft Defender XDR suchen

## Autor

**Florian Aschbichler**  
**Skylink GmbH**

## Disclaimer

Die bereitgestellten Queries dienen als Hilfsmittel für Analyse, Threat Hunting und Incident Response. Sie müssen vor produktiver Nutzung an die jeweilige Kundenumgebung, Datenverfügbarkeit und Fragestellung angepasst werden.

Eine Query allein ersetzt keine vollständige forensische Bewertung oder Incident-Response-Analyse.