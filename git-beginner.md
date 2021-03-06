# Git超入門

## バージョン管理システムの構成

Gitでファイルのバージョン管理する場合は、以下の図のようにファイルを集中管理する **「共用リモートレポジトリ」** があり、複数のファイル編集の作業者が自分のローカルのPCで編集作業をする構成が一般的である。
各編集者は自分のローカルPCに、共用リモートレポジトリを複製し **「ローカルレポジトリ」** を作成しローカルレポジトリ上で自分の必要な編集を行います。編集完了後に共用リモートレポジトリにアップロードし全員に共有できるようにします。

![](img/git-system-overview.png)

## レポジトリの構成
gitのレポジトリは、過去の変更履歴を保存するコミット履歴と、コミット前のファイルの変更状態を保存するインデックスとワークツリーという保存領域を持っています。

![](img/git-repo-after-clone.png)

直接ファイルをエディタなどで変更するとワークツリーの中が書き換わります。コミットをして変更履歴を残す場合は、直接ワークツリーからコミットを作成するのではなく、ワークツリーの中から次のコミットに必要な変更の全部または一部などをインデックスに適用（ステージング）してコミットする状態を作成します。

![](img/git-repo-staging.png)

インデックスへの適用がコミットしても良い単位になったら、コミットを行い履歴を追加作成します。この時コミットはワークツリーではなくインデックスから行われるため、新たな変更をワークツリーにして編集していても問題ありません。

![](img/git-repo-commit.png)


## バージョン管理の基本的な流れ
上記のようなシステム構成で、ファイルのバージョン管理をする場合の最も基本的な流れは以下のようになります。

1. [共用リモートレポジトリからローカルレポジトリへの複製 `(clone)`](git-clone.md)
1. [ローカルレポジトリでの変更をレポジトリに追加 `(add)`](git-add.md)
1. [追加した変更履歴をローカルレポジトリに保存 `(commit)`](git-commit.md)
1. [最新の共用リモートレポジトリを取り込み `(pull)`](git-pull.md)
1. [ローカルレポジトリの変更を共用リモートレポジトリに保存 `(push)`](git-push.md)

---
