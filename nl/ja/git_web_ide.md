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

# Eclipse Orion Web IDE での Git の作業
{: #git_web_ide}

Eclipse Orion {{site.data.keyword.webide}} で、多数の一般的な Git コマンドを実行できます。

どこでコーディングする場合でも、一般的なタスクの実行に際してはこのクイック・リファレンスを使用できます。 可能な場合は、Git コマンドと Web IDE の同等のコマンドが共に表示されます。 

## ローカル・ブランチの作成
{: #create_branch}

### Eclipse Orion Web IDE
{: #create_branch_web}

1. **「参照」**リストをクリックします。

1. **「新規ブランチ」**をクリックします。

2. ブランチ名を入力して、**「実行依頼」**をクリックします。

### Git 端末
{: #create_branch_cmd}
1. `git branch <branchname>` と入力し、Enter キーを押します。

## ローカル・ブランチに関する作業
{: #start_working_on_branch}

### Eclipse Orion Web IDE
{: #start_working_on_branch_web}
1. **「参照」**リストをクリックし、**「ローカル」**を展開します。

2. 変更するブランチのチェックアウト・アイコン <img  class="inline" src="./images/checkout.png" alt="チェックアウト・アイコン"> をクリックします。

1. 選択したブランチが**「参照」**リストに表示されていることを確認します。

### Git 端末
{: #start_working_on_branch_cmd}
1. ローカル・ブランチを表示するには、`git branch -l` と入力し、Enter キーを押します。

2. `git checkout <branchname>` と入力し、Enter キーを押します。


## ローカル・ブランチを更新してリモート・ブランチの変更を含める
{: #update_branch}

### Eclipse Orion Web IDE
{: #update_branch_web}

1. **「同期化」**をクリックします。

1. 矛盾が見つかった場合は、[矛盾を解決](#resolve_a_rebase_conflict)します。

### Git 端末
{: #update_branch_cmd}

1. `git pull` と入力し、Enter キーを押します。

## ローカル・ブランチの削除
{: #delete_branch}

### Eclipse Orion Web IDE
{: #delete_branch_web}
1. 削除するブランチがチェックアウトされていないことを確認します。 そのブランチがチェックアウトされている場合は、[別のブランチをチェックアウト](#start_working_on_branch)してください。

1. **「参照」**リストをクリックし、**「ローカル」**を展開します。

2. 削除するローカル・ブランチの**「削除」** <img class="inline"  src="./images/delete.png" alt="「削除」アイコン"> をクリックします。

### Git 端末
{: #delete_branch_cmd}

1. `git branch -d <branchname>` と入力し、Enter キーを押します。

##ローカルの変更をリモート・ブランチに強制的にプッシュする
{: #force_push}

参照されるリモート・ブランチの内容に、アクティブ・ローカル・ブランチの内容を上書きします。

**重要:** ローカル・ブランチをリモート・ブランチに強制的にプッシュすると、リモート・ブランチでのコミットが失われる可能性があります。

### Eclipse Orion Web IDE
{: #force_push_web}

1. 「作業ディレクトリーの変更」セクションの「発信」セクションで、**「プッシュ」**の矢印をクリックします。
2. **「ブランチを強制プッシュ」**をクリックします。
3. 警告を確認します。

### Git 端末
{: #force_push_cmd}

1. `git push <origin> <remote branch> -f` と入力し、Enter キーを押します。

## アクティブ・ローカル・ブランチから未ステージング変更を廃棄する
{: #discard_changes}

### Eclipse Orion Web IDE
{: #discard_changes_web}

1. 「作業ディレクトリーの変更」セクションで、廃棄する変更が含まれる変更済みファイルそれぞれのチェック・ボックスを選択します。
2. チェックアウト・アイコン <img class="inline"  src="./images/discard.png" alt="選択したファイルをチェックアウトして変更をすべて廃棄する"> をクリックします。

### Git 端末
{: #discard_changes_cmd}

1. `git checkout -- path/to/file/filename` と入力して、ファイルに加えられた変更を廃棄します。

## ファイルをコミットしてリモート・ブランチにプッシュする
{: #commit}

### Eclipse Orion Web IDE
{: #commit_web}

1. 「作業ディレクトリーの変更」セクションで、コミットするファイルそれぞれのチェック・ボックスを選択します。

3. **「コミット・メッセージを入力」**フィールドに、変更を説明するメッセージを入力します。

  **ヒント**: 詳細なコミット・メッセージを入力してください。 このメッセージは、変更が必要だった理由がそれだけで他のユーザーに十分伝わるように詳しく指定する必要があります。 参考になるチームの Issue Tracker の項目へのリンクを含めることができます。 コミット・メッセージの最初の行は、50 文字未満にする必要があります。 他のテキストを追加する前に、ブランク行を追加してください。

4. **「コミット」**をクリックします。

5. **「プッシュ」**をクリックします。

### Git 端末
{: #commit_cmd}

1. `git status` と入力し、Enter キーを押します。

2. コミットする変更を確認します。 コミットするファイルがすべてリストされていれば、次に進みます。 コミットするファイルが未ステージングなら、まずそれをステージングします。

3. `git commit` と入力し、Enter キーを押します。

4. コミット・サマリーを入力し、ブランク行を追加して、コミットの説明を追加します。

  **ヒント**: コミット・サマリーは 50 文字未満にする必要があります。 コミットの説明は、変更が必要だった理由がそれだけで他のユーザーに十分伝わるように詳しく指定する必要があります。 参考になるチームの Issue Tracker の項目へのリンクを含めることができます。

5. コミット・メッセージを保存します。

  **注:** コミット・メッセージを保存して Vim (ここでは、これがデフォルトのテキスト・エディターであると想定しています) を閉じるには、Esc キーを押し、`:wq` と入力して、Enter キーを押します。

4. `git push` と入力し、Enter キーを押します。

## コミット履歴の表示
{: #view_commit_history}

### Eclipse Orion Web IDE
{: #view_commit_history_web}

1. 「アクティブ・ブランチ」セクションで、**「履歴」**を展開して、そのブランチのコミット履歴を表示します。

  コミット履歴は関連ビジュアル・グラフとして表示することもできます。

1. **グラフィカル表現切り替え**アイコン <img  class="inline" src="./images/graphicalhistoryicon.png" alt="グラフィカル履歴アイコン"> をクリックします。

  切り替えると、アクティブ・ブランチのコミット履歴と着信変更または発信変更が関連グラフとして描画されます。  ビジュアル表示では、コミットとそれが行われたブランチがすべて示されます。

  <img class="screen-shot" src="./images/visualhistoryexample.png" alt="ビジュアル・コミット履歴">

### Git 端末
{: #view_commit_history_cmd}

1. `git log` と入力し、Enter キーを押します。

2. コミッターのコミットを参照します。
 * さらに項目を表示するには、Page Down キーを押します。
 * 前の項目を表示するには、Page Up キーを押します。

3. 項目の表示を中止するには、Q キーを押します。

## コミットによる変更の比較
{: #compare_changes}

### Eclipse Orion Web IDE
{: #compare_changes_web}

1. コミット履歴を表示して、コミットを見つけます。 詳しくは、[コミット履歴の表示](#view_commit_history)を参照してください。

2. コミットをクリックしてその詳細を表示します。

3. ファイルの変更内容を確認するには、**>** をクリックします。

  **注:** コミットによって行が変更された場合、元の行にはピンクの陰影が付けられ、新しい行には緑色の陰影が付けられます。  同様に、コミットによって追加された行には緑色の陰影が付けられ、コミットによって削除された行にはピンクの陰影が付けられます。

### Git 端末
{: #compare_changes_cmd}

1. `git log -p` と入力し、Enter キーを押します。

  **注:** 特定の数のコミットのみ表示するには、`git log -p -<number_of_commits_to_view>` と入力します。

2. コミットをナビゲートします。
 * さらに項目を表示するには、Page Down キーを押します。
 * 前の項目を表示するには、Page Up キーを押します。

3. 変更を確認します。

  **注:** コミットによって行が変更された場合、元の行は赤色のテキストで表示され、先頭に負符号 (-) が付きます。 新しい行は緑色のテキストで表示され、先頭に正符号 (+) が付きます。  同様に、コミットによって追加された行は緑色のテキストで表示され、先頭に正符号 (+) が付きます。 コミットによって削除された行は赤色のテキストで表示され、先頭に負符号 (-) が付きます。

1. 項目の表示を中止するには、Q キーを押します。

## 最後のコミットの変更
{: #modify_last_commit}

  **注:** 最後のコミットをリモート・リポジトリーにプッシュした後に変更すると、コミット履歴が書き換えられることになります。 この変更は、プロジェクト内で他のコントリビューターがコミットに失敗したりその他の問題に直面したりする原因になる可能性があります。 リモート・リポジトリーにプッシュしたコミットを変更する前に、その操作の意味をよく理解するようにしてください。

### Eclipse Orion Web IDE
{: #modify_last_commit_web}
1. コミットに追加する項目のチェック・ボックスを選択します。

1. **「前のコミットの修正」**チェック・ボックスを選択します。

2. 必要であれば、新しいコミット・メッセージを入力します。

3. **「コミット」**をクリックします。

### Git 端末
{: #modify_last_commit_cmd}

1. 状況を確認します。 必要に応じて、ファイルをステージングするかステージング解除します。

2. `git commit --amend` と入力し、Enter キーを押します。

3. テキスト・エディターで、コミット・メッセージを受け入れるか変更します。

  **注:** コミット・メッセージを保存して Vim (ここでは、これがデフォルトのテキスト・エディターであると想定しています) を閉じるには、Esc キーを押し、`:wq` と入力して、Enter キーを押します。

## コミットへのタグ付け
{: #tag_commit}

### Eclipse Orion Web IDE
{: #tag_commit_web}

1. コミット履歴を表示して、コミットを見つけます。 詳しくは、[コミット履歴の表示](#view_commit_history)を参照してください。

2. コミットをクリックしてその詳細を表示します。

2. コミット・ペインで、**「コミットのタグを作成」** <img class="inline"  src="./images/tag.png" alt="コミットのタグを作成"> をクリックします。

3. 名前フィールドに、タグ・テキストを入力します。 **「実行依頼」**をクリックします。

### Git 端末
{: #tag_commit_cmd}

1. コミット履歴を表示して、タグ付けするコミットの ID を取得します。 詳しくは、[コミット履歴の表示](#view_commit_history)を参照してください。

2. `git tag -a <tag_text> <commit_id>` と入力し、Enter キーを押します。

## コミッター名と E メール・アドレスの変更
{: #change_the_committer_name_and_email_address}

### Eclipse Orion Web IDE
{: #change_info_web}
1. 構成アイコン <img class="inline" src="./images/configurations.png" alt="構成アイコン"> をクリックします。

3. user.email と user.name の値を更新して、ユーザーの E メール・アドレスと名前を変更します。 **「実行依頼」**をクリックして各変更を保存します。

### Git 端末
{: #change_info_cmd}

単一リポジトリーで名前と E メール・アドレスを更新するには、次のようにします。

1. `git config user.email "<your@email.com>"` と入力し、Enter キーを押します。

2. `git config user.name "<Your Name>"` と入力し、Enter キーを押します。

すべてのリポジトリーで名前と E メール・アドレスを更新するには、次のようにします。

1. `git config --global user.email "<your@email.com>"` と入力し、Enter キーを押します。

2. `git config --global user.name "<Your Name>"` と入力し、Enter キーを押します。

##コミットを元に戻す
{: #revert}

コミットによってアクティブ・ブランチに加えられた変更を戻します。

### Eclipse Orion Web IDE
{: #revert_web}

1. 「履歴」で、コミットを選択します。

2. 「戻る」アイコン <img class="inline" src="./images/revert.png" alt="「戻る」アイコン"> をクリックします。

### Git 端末
{: #revert_cmd}

1. `git revert <commit ID>` と入力し、Enter キーを押します。

## 変更のマージ
{: #merge_changes}

ソース・ブランチから宛先ブランチに変更をデリバリーする必要があるときは、まずマージしなければなりません。 通常、ソース・ブランチは変更が行われたブランチであり、宛先ブランチはマスター・ブランチです。

### Eclipse Orion Web IDE
{: #merge_changes_web}

1. マージするブランチを決定します。

2. 宛先ブランチをチェックアウトします。 詳しくは、[ローカル・ブランチに関する作業](#start_working_on_branch)を参照してください。

 <img class="screen-shot" src="./images/destinationbranch.png" alt="宛先ブランチのチェックアウト">

1. **「参照」**リストをクリックして、**「ローカル」**を展開し、ソース・ブランチの名前をクリックします。 ソース・ブランチに含まれる変更が「着信」セクションに表示されます。

  <img class="screen-shot" src="./images/sourcebranch.png" alt="「着信」セクションに表示されたソース・ブランチの変更">

1. 「着信」セクションで、**「統合」**アイコン <img  class="inline" src="./images/mergeicon.png" alt="「着信」セクションの「統合」アイコン"> をクリックします。

1. **「参照」**リストで、先ほど変更をマージしたブランチのチェックアウト・アイコンをクリックします。

1. 変更をデリバリーする場合は、**「プッシュ」**をクリックします。 そうしない場合は、この時点で、テスト・デプロイメントを作成して、すべてが予想どおりに機能するかどうかを確認できます。

### Git 端末
{: #merge_changes_cmd}

1. マージするブランチを決定します。

2. 宛先ブランチをチェックアウトします。 詳しくは、[ローカル・ブランチに関する作業](#start_working_on_branch)を参照してください。

3. `git merge <source_name>` と入力し、Enter キーを押します。


## マージの競合の解決
{: #resolve_a_merge_conflict}

### Eclipse Orion Web IDE
{: #resolve_a_merge_conflict_web}

1. 「変更されたファイル」ペインで、競合があるファイルのリストを確認します。

2. Web IDE で、競合がある各ファイルを開きます。

3. 競合している各変更を解決します。

  **注:** 残しておきたくないテキストはすべて削除してください。 競合はそれぞれ次の形式で示されます。

		<<<<<<< HEAD
		Text in checked out branch.
		=======
		Text in merged branch.
		>>>>>>> commit_ID_from_merged_branch
4. 競合ファイルそれぞれのチェック・ボックスを選択します。 マージ・コミット・メッセージを入力し、**「コミット」**をクリックします。

### Git 端末
{: #resolve_a_merge_conflict_cmd}

1. 競合があるファイルの名前を、Git メッセージで確認します。

2. 競合があるファイルをテキスト・エディターで開きます。

3. 競合している各変更を解決して、ファイルを保存します。

  **注:** 残しておきたくないテキストはすべて削除してください。 競合はそれぞれ次の形式で示されます。

		<<<<<<< HEAD
		Text in checked out branch.
		=======
		Text in merged branch.
		>>>>>>> merged_branch
4. 変更した各ファイルをステージングした後、マージをコミットします。

## ブランチのリベース
{: #rebase_branches}

### Eclipse Orion Web IDE
{: #rebase_branches_web}

1. リベースするブランチを決定します。 ソース・ブランチの内容を宛先ブランチにリベースすることになります。

2. 宛先ブランチをチェックアウトします。 詳しくは、[ローカル・ブランチに関する作業](#start_working_on_branch)を参照してください。

1. **「参照」**リストをクリックします。

1. ソース・ブランチの名前をクリックします。

1. 「着信」セクションで、リベース・アイコン <img  class="inline" src="./images/rebase.png" alt="リベース・アイコン"> をクリックします。

5. 矛盾が見つかった場合は、[矛盾を解決](#resolve_a_rebase_conflict)します。

6. 必要な回数だけ前のステップを繰り返して、リベース操作を完了します。

1. **「参照」**リストをクリックして、**「情報」**を展開し、ソース・ブランチの名前をクリックします。

1. **「プッシュ」**をクリックします。

### Git 端末
{: #rebase_branches_cmd}

1. `git checkout <destination_branchname>` と入力して Enter キーを押すことにより、更新するブランチをチェックアウトします。

2. `git rebase <source_branchname>` と入力し、Enter キーを押します。

3. 矛盾が見つかった場合は、[矛盾を解決](#resolve_a_rebase_conflict)します。

5. 必要な回数だけ前のステップを繰り返して、リベース操作を完了します。

  **注:** リベース操作を中止するには、`git rebase --abort` と入力し、Enter キーを押します。

## リベースの競合の解決
{: #resolve_a_rebase_conflict}

### Eclipse Orion Web IDE
{: #resolve_a_rebase_conflict_web}

1. 「作業ディレクトリーの変更」セクションで、競合しているファイルのリストを確認します。

2. Web IDE で、競合がある各ファイルを開きます。

3. 競合している各変更を解決します。

  **注:** 残しておきたくないテキストはすべて削除してください。 競合はそれぞれ次の形式で示されます。

		<<<<<<< HEAD
		Text in checked out branch.
		=======
		Text in merged branch.
		>>>>>>> commit_ID_from_merged_branch
4. リベース・ペインで、修正したファイルそれぞれのチェック・ボックスを選択し、**「続行」**をクリックします。

### Git 端末
{: #resolve_a_rebase_conflict_cmd}

1. 競合があるファイルの名前を、Git メッセージで確認します。

2. 競合があるファイルをテキスト・エディターで開きます。

3. 競合している各変更を解決して、ファイルを保存します。

  **注:** 残しておきたくないテキストはすべて削除してください。 競合はそれぞれ次の形式で示されます。

		<<<<<<< HEAD
		Text in checked out branch.
		=======
		Text in merged branch.
		>>>>>>> merged_branch
4. 変更した各ファイルをステージングします。

5. `git rebase --continue` と入力して Enter キーを押すことにより、リベース操作を再開します。
