# CI auf dem Windows-Runner (`heim-pc`) – Übergabe

*Stand 01.10.2026, geprüft auf `main`.*

**Dieses Repo hat keine eigenen GitHub-Actions-Workflows** (kein `.github/`). Es enthält nur die gebaute Spielseite (`index.html`) und eine README.

Einziger Actions-Lauf ist GitHubs eingebauter **„pages build and deployment“** (GitHub Pages, Quelle: Branch `main`, Ordner `/`). Den verwaltet GitHub selbst, er hat keine Workflow-Datei und lässt sich nicht per `RUNNER_LABEL` auf einen eigenen Runner umstellen. Bisher liefen alle Pages-Builds erfolgreich (zuletzt für v0.15). Falls er wegen des Ausgabenlimits ausfällt, wäre die Alternative eine eigene Workflow-Datei mit `actions/upload-pages-artifact` + `actions/deploy-pages` auf `runs-on: ${{ vars.RUNNER_LABEL || 'ubuntu-latest' }}` und Pages-Quelle „GitHub Actions“ – die Schritte sind plattformneutral.

Die Seite wird im privaten Repo `somasomarum/aquarell` mit `tools/pages.sh` (sh-Skript) gebaut, nicht hier.

Workflow-Dateien bitte nur vom lokalen Claude des Nutzers anlegen/ändern (Absprache zwischen den Sessions).
