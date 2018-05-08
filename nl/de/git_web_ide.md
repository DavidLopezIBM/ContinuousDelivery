---

copyright:
  years: 2017, 2018
lastupdated: "2018-3-23"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}
{:pre: .pre}

# Mit Git in der Eclipse Orion-Web-IDE arbeiten
{: #git_web_ide}

Sie können viele allgemeine Git-Befehle in der Eclipse Orion-Web-IDE ausführen.

Unabhängig von dem Standort, an dem Sie Code schreiben, können Sie diese Kurzübersicht verwenden, um allgemeine Tasks auszuführen. Wenn möglich werden die Git-Befehle mit ihren Entsprechungen in der Web-IDE gezeigt. 

## Lokalen Zweig erstellen
{: #create_branch}

### Eclipse Orion-Web-IDE
{: #create_branch_web}

1. Klicken Sie auf die Liste **Referenz**.

1. Klicken Sie auf **Neuer Zweig**.

2. Geben Sie einen Namen für Ihren Zweig ein und klicken Sie auf **Abschicken**.

### Git-Terminal
{: #create_branch_cmd}
1. Geben Sie `git branch <branchname>` ein und drücken Sie die Eingabetaste.

## Lokalen Zweig bearbeiten
{: #start_working_on_branch}

### Eclipse Orion-Web-IDE
{: #start_working_on_branch_web}
1. Klicken Sie auf die Liste **Referenz** und expandieren Sie **Lokal**.

2. Klicken Sie für den Zweig, an dem Sie Änderungen vornehmen wollen, auf das Symbol für den Check-out <img  class="inline" src="./images/checkout.png" alt="Symbol für Checkout">.

1. Stellen Sie sicher, dass der von Ihnen ausgewählte Zweig in der Liste **Referenz** angezeigt wird.

### Git-Terminal
{: #start_working_on_branch_cmd}
1. Geben Sie zum Anzeigen Ihrer lokalen Zweige `git branch -l` ein und drücken Sie die Eingabetaste.

2. Geben Sie `git checkout <branchname>` ein und drücken Sie die Eingabetaste.


## Lokalen Zweig aktualisieren, um Änderungen des fernen Zweigs einzuschließen
{: #update_branch}

### Eclipse Orion-Web-IDE
{: #update_branch_web}

1. Klicken Sie auf **Synchronisieren**.

1. Wenn Konflikte auftreten, [beheben Sie sie](#resolve_a_rebase_conflict).

### Git-Terminal
{: #update_branch_cmd}

1. Geben Sie `git pull` ein und drücken Sie die Eingabetaste.

## Lokalen Zweig löschen
{: #delete_branch}

### Eclipse Orion-Web-IDE
{: #delete_branch_web}
1. Stellen Sie sicher, dass der zu löschende Zweig nicht ausgecheckt ist. Wenn dieser Zweig ausgecheckt ist,
[checken Sie einen anderen Zweig aus](#start_working_on_branch).

1. Klicken Sie auf die Liste **Referenz** und expandieren Sie **Lokal**.

2. Klicken Sie für den lokalen Zweig, den Sie entfernen möchten, auf **Löschen** <img class="inline"  src="./images/delete.png" alt="Symbol 'Löschen'">.

### Git-Terminal
{: #delete_branch_cmd}

1. Geben Sie `git branch -d <branchname>` ein und drücken Sie die Eingabetaste.

##Übertragung von lokalen Änderungen per Push-Operation an einen fernen Zweig erzwingen
{: #force_push}

Überschreiben Sie den Inhalt eines referenzierten fernen Zweigs mit dem Inhalt Ihres aktiven lokalen Zweigs.

**Wichtig:** Wenn Sie die Übertragung eines lokalen Zweigs per Push-Operation an einen fernen Zweig erzwingen,
verlieren Sie im fernen Zweig möglicherweise Commitoperationen.

### Eclipse Orion-Web-IDE
{: #force_push_web}

1. Klicken Sie im Abschnitt 'Arbeitsverzeichnisänderungen' im Abschnitt 'Ausgehend' auf den Pfeil für **Push-Operation durchführen**.
2. Klicken Sie auf **Push-Operation für Zweig erzwingen**.
3. Bestätigen Sie die Warnung.

### Git-Terminal
{: #force_push_cmd}

1. Geben Sie `git push <origin> <remote branch> -f` ein und drücken Sie die Eingabetaste.

## Änderungen, für die das Staging aufgehoben wurde, aus dem aktiven lokalen Zweig verwerfen
{: #discard_changes}

### Eclipse Orion-Web-IDE
{: #discard_changes_web}

1. Wählen Sie im Abschnitt 'Arbeitsverzeichnisänderungen' die Kontrollkästchen aller geänderten Dateien aus, deren Änderungen
Sie verwerfen wollen.
2. Klicken Sie auf das Symbol für Check-out <img class="inline"  src="./images/discard.png" alt="Ausgewählte Dateien auschecken, alle Änderungen verwerfen">.

### Git-Terminal
{: #discard_changes_cmd}

1. Geben Sie `git checkout -- path/to/file/filename` ein, um Änderungen an einer Datei zu verwerfen.

## Dateien festschreiben und Push-Operation an fernen Zweig durchführen
{: #commit}

### Eclipse Orion-Web-IDE
{: #commit_web}

1. Wählen Sie im Abschnitt 'Arbeitsverzeichnisänderungen' die Kontrollkästchen aller Dateien aus, die festgeschrieben werden sollen.

3. Geben Sie im Feld **Commitnachricht eingeben** eine Nachricht ein, die Ihre Änderungen beschreibt.

  **Tipp**: Geben Sie eine detaillierte Commitnachricht an. Ihre Nachricht sollte ausreichend Details enthalten,
sodass eine andere Person ohne weitere Informationen versteht, weshalb die Änderung erforderlich war. Sie können in den zu Ihrem Team
zugehörigen Tracker für Probleme einen Link zu einem Element einschließen, um Hilfe anzufordern. Die erste Zeile der Commitnachricht sollte weniger als 50 Zeichen enthalten. Fügen Sie eine leere Zeile hinzu, bevor Sie weiteren Text
hinzufügen.

4. Klicken Sie auf **Commit**.

5. Klicken Sie auf **Push-Operation durchführen**.

### Git-Terminal
{: #commit_cmd}

1. Geben Sie `git status` ein und drücken Sie die Eingabetaste.

2. Überprüfen Sie die festzuschreibenden Änderungen. Wenn alle Ihre Dateien für eine Commitoperation aufgelistet sind, fahren Sie
fort. Um Dateien festzuschreiben, für die das Staging aufgehoben wurde, müssen Sie zunächst das Staging für sie ausführen.

3. Geben Sie `git commit` ein und drücken Sie die Eingabetaste.

4. Geben Sie die Commitzusammenfassung ein, fügen Sie eine leere Zeile hinzu und fügen Sie die Beschreibung für die Commitoperation
hinzu.

  **Tipp**: Die Commitzusammenfassung sollte weniger als 50 Zeichen umfassen. Die Commitbeschreibung sollte genügend
Details bereitstellen, sodass auch eine andere Person ohne weitere Informationen versteht, warum die Änderung erforderlich war. Sie können in den zu Ihrem Team
zugehörigen Tracker für Probleme einen Link zu einem Element einschließen, um Hilfe anzufordern.

5. Commitnachricht speichern

  **Hinweis:** Um Ihre Commitnachricht zu speichern und Vim zu schließen, der möglicherweise Ihr
Standardtexteditor ist, drücken Sie die Escapetaste und geben Sie `:wq` ein; drücken Sie anschließend die Eingabetaste.

4. Geben Sie `git push` ein und drücken Sie die Eingabetaste.

## Commitprotokoll anzeigen
{: #view_commit_history}

### Eclipse Orion-Web-IDE
{: #view_commit_history_web}

1. Erweitern Sie im Abschnitt 'Aktiver Zweig' den Punkt **Protokoll**, um das Commitprotokoll für diesen Zweig
anzuzeigen.

  Das Commitprotokoll kann auch als verbundenes, grafisches Diagramm angezeigt werden.

1. Klicken Sie auf das Symbol **Grafische Darstellung ein-/ausschalten**
<img  class="inline" src="./images/graphicalhistoryicon.png" alt="Symbol für grafisches Protokoll">.

  Nach dem Einschalten werden das Commitprotokoll und alle eingehenden oder abgehenden Änderungen für den aktiven Zweig als verbundenes Diagramm gezeichnet.  Die grafische Darstellung zeigt alle Commitoperationen sowie die Zweige an, für die sie durchgeführt wurden.

  <img class="screen-shot" src="./images/visualhistoryexample.png" alt="Commit-Verlauf visualisieren">

### Git-Terminal
{: #view_commit_history_cmd}

1. Geben Sie `git log` ein und drücken Sie die Eingabetaste.

2. Navigieren Sie durch die Commitoperationen des Committers.
 * Drücken Sie zum Anzeigen weiterer Einträge auf die Taste zum Vorblättern.
 * Drücken Sie zum Anzeigen vorheriger Einträge auf die Taste zum Zurückblättern.

3. Drücken Sie die Taste 'Q', um die Anzeige von Einträgen zu stoppen.

## Durch eine Commitoperation eingeführte Änderungen vergleichen
{: #compare_changes}

### Eclipse Orion-Web-IDE
{: #compare_changes_web}

1. Zeigen Sie Ihr Commitprotokoll an und suchen Sie nach der Commitoperation. Weitere Informationen finden Sie in [Commitprotokoll anzeigen](#view_commit_history).

2. Zeigen Sie die Details der Commitoperation an, indem Sie auf die Commitoperation klicken.

3. Klicken Sie zum Überprüfen der an einer Datei vorgenommenen Änderungen auf **>**.

  **Hinweis:** Wenn durch eine Commitoperation die Änderung einer Zeile eingeführt wurde, wird die ursprüngliche
Zeile rosa und die neue Zeile grün schattiert.  In gleicher Weise werden Zeilen, die durch eine Commitoperation hinzugefügt wurden, grün
schattiert, und Zeilen, die aus einer Commitoperation entfernt wurden, werden rosa schattiert.

### Git-Terminal
{: #compare_changes_cmd}

1. Geben Sie `git log -p` ein und drücken Sie die Eingabetaste.

  **Hinweis:** Geben Sie `git log -p -<Anzahl_der_anzuzeigenden_Commits>` ein, um nur eine bestimmte Anzahl von Commitoperationen anzuzeigen.

2. Navigieren Sie durch die Commitoperationen.
 * Drücken Sie zum Anzeigen weiterer Einträge auf die Taste zum Vorblättern.
 * Drücken Sie zum Anzeigen vorheriger Einträge auf die Taste zum Zurückblättern.

3. Überprüfen Sie die Änderungen.

  **Hinweis:** Wenn durch eine Commitoperation die Änderung einer Zeile eingeführt wurde, wird die ursprüngliche
Zeile in rotem Text angezeigt und beginnt mit einem Minuszeichen (-). Die neue Zeile wird in grünem Text angezeigt und beginnt mit einem
Pluszeichen (+).  In gleicher Weise werden Zeilen, die durch eine Commitoperation hinzugefügt wurden, in grünem Text angezeigt und beginnen
mit einem Pluszeichen. Zeilen, die durch eine Commitoperation
entfernt wurden, werden in rotem Text angezeigt und beginnen mit einem Minuszeichen.

1. Drücken Sie die Taste 'Q', um die Anzeige von Einträgen zu stoppen.

## Letzte Commitoperation ändern
{: #modify_last_commit}

  **Hinweis:** Wenn Sie die letzte Commitoperation ändern, nachdem Sie sie mit einer Push-Operation
an ein fernes Repository übertragen haben, erstellen Sie das Commitprotokoll erneut. Diese Änderung verursacht für die übrigen Bearbeiter in Ihrem Projekt möglicherweise Commitfehler und weitere Probleme. Seien Sie sich im Klaren darüber, welche Schritte Sie vornehmen, wenn Sie eine Commitoperation
ändern, die mit einer Push-Operation an ein fernes Repository übertragen wurde.

### Eclipse Orion-Web-IDE
{: #modify_last_commit_web}
1. Wählen Sie die Kontrollkästchen der Elemente aus, die der Commitoperation hinzugefügt werden sollen.

1. Wählen Sie das Kontrollkästchen **Vorheriges Commit ergänzen** aus.

2. Geben Sie, falls erforderlich, eine neue Commitnachricht ein.

3. Klicken Sie auf **Commit**.

### Git-Terminal
{: #modify_last_commit_cmd}

1. Überprüfen Sie Ihren Status. Führen Sie wie erforderlich für Dateien ein Staging aus bzw. heben Sie das Staging auf.

2. Geben Sie `git commit --amend` ein und drücken Sie die Eingabetaste.

3. Akzeptieren Sie die Commitnachricht in Ihrem Texteditor oder ändern Sie sie.

  **Hinweis:** Um Ihre Commitnachricht zu speichern und Vim zu schließen, der möglicherweise Ihr
Standardtexteditor ist, drücken Sie die Escapetaste und geben Sie `:wq` ein; drücken Sie anschließend die Eingabetaste.

## Commit taggen
{: #tag_commit}

### Eclipse Orion-Web-IDE
{: #tag_commit_web}

1. Zeigen Sie Ihr Commitprotokoll an und suchen Sie nach der Commitoperation. Weitere Informationen finden Sie in [Commitprotokoll anzeigen](#view_commit_history).

2. Zeigen Sie die Details der Commitoperation an, indem Sie auf die Commitoperation klicken.

2. Klicken Sie im Teilfenster 'Commit' auf **Tag für die Commitoperation erstellen**
<img class="inline"  src="./images/tag.png" alt="Tag für die Commitoperation erstellen">.

3. Geben Sie Ihren Tagtext in das Namensfeld ein. Klicken Sie auf **Abschicken**.

### Git-Terminal
{: #tag_commit_cmd}

1. Zeigen Sie das Commitprotokoll an und rufen Sie die ID der Commitoperation ab, die getaggt werden soll. Weitere Informationen finden Sie in [Commitprotokoll anzeigen](#view_commit_history).

2. Geben Sie `git tag -a <tag_text> <commit_id>` ein und drücken Sie die Eingabetaste.

## Committername und E-Mail-Adresse ändern
{: #change_the_committer_name_and_email_address}

### Eclipse Orion-Web-IDE
{: #change_info_web}
1. Klicken Sie auf das Symbol für 'Konfiguration' <img class="inline" src="./images/configurations.png" alt="Symbol für Konfiguration">.

3. Ändern Sie die Benutzer-E-Mail-Adresse und den Namen, indem Sie die Werte 'user.email' und 'user.name' aktualisieren. Klicken
Sie auf **Abschicken**, um die einzelnen Änderungen zu speichern.

### Git-Terminal
{: #change_info_cmd}

Gehen Sie wie folgt vor, um Ihren Namen und Ihre E-Mail-Adresse für ein einzelnes Repository zu aktualisieren:

1. Geben Sie `git config user.email "<your@email.com>"` ein und drücken Sie die Eingabetaste.

2. Geben Sie `git config user.name "<Your Name>"` ein und drücken Sie die Eingabetaste.

Gehen Sie wie folgt vor, um Ihren Namen und Ihre E-Mail-Adresse für alle Repositorys zu aktualisieren:

1. Geben Sie `git config --global user.email "<your@email.com>"` ein und drücken Sie die Eingabetaste.

2. Geben Sie `git config --global user.name "<Your Name>"` ein und drücken Sie die Eingabetaste.

##Commitoperation zurücksetzen
{: #revert}

Setzen Sie die Änderungen zurück, die durch eine Commitoperation in Ihrem aktiven Zweig eingeführt wurden.

### Eclipse Orion-Web-IDE
{: #revert_web}

1. Wählen Sie unter 'Protokoll' eine Commitoperation aus.

2. Klicken Sie auf das Symbol für Zurücksetzung <img class="inline" src="./images/revert.png" alt="Symbo für Zurücksetzung">.

### Git-Terminal
{: #revert_cmd}

1. Geben Sie `git revert <commit ID>` ein und drücken Sie die Eingabetaste.

## Änderungen zusammenführen
{: #merge_changes}

Wenn Sie Änderungen von einem als Quelle verwendeten Zweig für einen als Ziel verwendeten Zweig bereitstellen wollen, müssen Sie sie zunächst
zusammenführen. In der Regel ist der als Quelle verwendete Zweig der Zweig, in dem Sie Änderungen durchgeführt haben, und der als Ziel
verwendete Zweig ist Ihr Masterzweig.

### Eclipse Orion-Web-IDE
{: #merge_changes_web}

1. Entscheiden Sie, welche Zweige zusammengeführt werden sollen.

2. Checken Sie den als Ziel verwendeten Zweig aus. Weitere Informationen finden Sie in [Lokalen Zweig bearbeiten](#start_working_on_branch).

 <img class="screen-shot" src="./images/destinationbranch.png" alt="Den als Ziel verwendeten Zweig auschecken">

1. Klicken Sie auf die Liste **Referenz**, expandieren Sie **Lokal** und klicken Sie auf den Namen
des als Quelle verwendeten Zweigs. Die Änderungen aus dem als Quelle verwendeten Zweig werden im Abschnitt 'Eingehend' angezeigt.

  <img class="screen-shot" src="./images/sourcebranch.png" alt="Aus dem als Quelle verwendeten Ziel stammende Änderungen, die im Abschnitt 'Eingehend' angezeigt werden">

1. Klicken Sie im Abschnitt 'Eingehend' auf das Symbol für **Zusammenführen**
<img  class="inline" src="./images/mergeicon.png" alt="Symbol für Zusammenführen im Abschnitt 'Eingehend'">

1. Klicken Sie in der Liste **Referenz** für den Zweig, mit dem Sie gerade die Änderungen zusammengeführt haben, auf das Symbol für Check-out.

1. Wenn Sie die Änderungen bereitstellen wollen, klicken Sie auf **Push-Operation durchführen**. Andernfalls
können Sie an diesem Zeitpunkt eine Testbereitstellung vornehmen, um sicherzustellen, dass die gesamte Ausführung wie erwartet funktioniert.

### Git-Terminal
{: #merge_changes_cmd}

1. Entscheiden Sie, welche Zweige zusammengeführt werden sollen.

2. Checken Sie den als Ziel verwendeten Zweig aus. Weitere Informationen finden Sie in [Lokalen Zweig bearbeiten](#start_working_on_branch).

3. Geben Sie `git merge <source_name>` ein und drücken Sie die Eingabetaste.


## Zusammenführungskonflikt beheben
{: #resolve_a_merge_conflict}

### Eclipse Orion-Web-IDE
{: #resolve_a_merge_conflict_web}

1. Überprüfen Sie im Teilfenster 'Geänderte Dateien' die Liste der Dateien, die Konflikte enthalten.

2. Öffnen Sie in der Web-IDE jede Datei, die Konflikte enthält.

3. Beheben Sie alle in Konflikt stehenden Änderungen.

  **Hinweis:** Löschen Sie jeglichen Text, den Sie nicht beibehalten möchten. Konflikte haben folgendes Format:

		<<<<<<< KOPFZEILE
		Text im ausgecheckten Zweig.
		=======
		Text im zusammengeführten Zweig.
		>>>>>>> Commit-ID_des_zusammengeführten_Zweigs
4. Wählen Sie für jede der Dateien, in denen Konflikte vorhanden sind, das Kontrollkästchen aus. Geben Sie eine
Commitnachricht für die Zusammenführung ein und klicken Sie auf **Commit**.

### Git-Terminal
{: #resolve_a_merge_conflict_cmd}

1. Überprüfen Sie die Git-Nachricht auf Namen von Dateien, die Konflikte enthalten.

2. Öffnen Sie in einem Texteditor eine Datei mit Konflikten.

3. Beheben Sie alle in Konflikt stehenden Änderungen und speichern Sie anschließend die Datei.

  **Hinweis:** Löschen Sie jeglichen Text, den Sie nicht beibehalten möchten. Konflikte haben folgendes Format:

		<<<<<<< KOPFZEILE
		Text im ausgecheckten Zweig.
		=======
		Text im zusammengeführten Zweig.
		>>>>>>> zusammengeführter_Zweig
4. Führen Sie für jede geänderte Datei ein Staging aus und schreiben Sie die Zusammenführung anschließend fest.

## Zweige mit Referenzversionen aktualisieren
{: #rebase_branches}

### Eclipse Orion-Web-IDE
{: #rebase_branches_web}

1. Entscheiden Sie, welche Zweige mit Referenzversionen aktualisiert werden sollen. Sie führen für die Inhalte des als Quelle
verwendeten Zweigs eine Aktualisierung in den als Ziel verwendeten Zweig durch.

2. Checken Sie den als Ziel verwendeten Zweig aus. Weitere Informationen finden Sie in [Lokalen Zweig bearbeiten](#start_working_on_branch).

1. Klicken Sie auf die Liste **Referenz**.

1. Klicken Sie auf den Namen des als Quelle verwendeten Zweigs.

1. Klicken Sie im Abschnitt 'Eingehend' auf das Symbol für das Aktualisieren mit einer Referenzversion
<img  class="inline" src="./images/rebase.png" alt="Symbol 'Aktualisieren mit einer Referenzversion">.

5. Wenn Konflikte auftreten, [beheben Sie sie](#resolve_a_rebase_conflict).

6. Wiederholen Sie die vorherigen Schritte so häufig wie erforderlich, um die Operation zum Aktualisieren mit Referenzversionen
abzuschließen.

1. Klicken Sie auf die Liste **Referenz**, erweitern Sie **Ursprung** und klicken Sie auf den
Namen des als Quelle verwendeten Zweigs.

1. Klicken Sie auf **Push-Operation durchführen**.

### Git-Terminal
{: #rebase_branches_cmd}

1. Checken Sie den zu aktualisierenden Zweig aus, indem Sie `git checkout <Name_des_als_Ziel_verwendeten_Zweigs>` eingeben und die Eingabetaste drücken.

2. Geben Sie `git rebase <source_branchname>` ein und drücken Sie die Eingabetaste.

3. Wenn Konflikte auftreten, [beheben Sie sie](#resolve_a_rebase_conflict).

5. Wiederholen Sie die vorherigen Schritte so häufig wie erforderlich, um die Operation zum Aktualisieren mit Referenzversionen
abzuschließen.

  **Hinweis:** Geben Sie zum Stoppen der Operation zum Aktualisieren mit Referenzversionen
`git rebase --abort` ein und drücken Sie die Eingabetaste.

## Konflikt bei der Aktualisierung mit Referenzversionen beheben
{: #resolve_a_rebase_conflict}

### Eclipse Orion-Web-IDE
{: #resolve_a_rebase_conflict_web}

1. Überprüfen Sie im Abschnitt 'Arbeitsverzeichnisänderungen' die Liste mit den Dateien, die in Konflikt zueinander stehen.

2. Öffnen Sie in der Web-IDE jede Datei, die Konflikte enthält.

3. Beheben Sie alle in Konflikt stehenden Änderungen.

  **Hinweis:** Löschen Sie jeglichen Text, den Sie nicht beibehalten möchten. Konflikte haben folgendes Format:

		<<<<<<< KOPFZEILE
		Text im ausgecheckten Zweig.
		=======
		Text im zusammengeführten Zweig.
		>>>>>>> Commit-ID_des_zusammengeführten_Zweigs
4. Wählen Sie im Teilfenster für die Aktualisierung mit Referenzversionen für jede korrigierte Datei das Kontrollkästchen aus und
klicken Sie auf **Weiter**.

### Git-Terminal
{: #resolve_a_rebase_conflict_cmd}

1. Überprüfen Sie die Git-Nachricht auf Namen von Dateien, die Konflikte enthalten.

2. Öffnen Sie in einem Texteditor eine Datei mit Konflikten.

3. Beheben Sie alle in Konflikt stehenden Änderungen und speichern Sie anschließend die Datei.

  **Hinweis:** Löschen Sie jeglichen Text, den Sie nicht beibehalten möchten. Konflikte haben folgendes Format:

		<<<<<<< KOPFZEILE
		Text im ausgecheckten Zweig.
		=======
		Text im zusammengeführten Zweig.
		>>>>>>> zusammengeführter_Zweig
4. Führen Sie für jede geänderte Datei ein Staging durch.

5. Nehmen Sie die Operation für das Aktualisieren mit Referenzversionen wieder auf, indem Sie
`git rebase --continue` eingeben und die Eingabetaste drücken.
