---
title: リポジトリをフォークする
redirect_from:
  - /fork-a-repo
  - /forking
  - /articles/fork-a-repo
  - /github/getting-started-with-github/fork-a-repo
  - /github/getting-started-with-github/quickstart/fork-a-repo
intro: フォークは、リポジトリのコピーです。 リポジトリをフォークすることにより、オリジナルのプロジェクトに影響を与えることなく変更を自由にテストできます。
permissions: '{% data reusables.enterprise-accounts.emu-permission-fork %}'
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
  - Issues
  - Notifications
  - Accounts
ms.openlocfilehash: b6f98f30c67f14fab1da3658e42e8eba67f5f50c
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2022
ms.locfileid: '147717574'
---
## フォークについて

最も一般的には、フォークは、書き込みアクセス権がない他のユーザーのプロジェクトに変更を提案し、他のユーザーのプロジェクトを自分のアイデアの出発点として使用するために使用されます。 リポジトリをフォークすると、リポジトリのコピーを作成し、上流リポジトリに影響を与えずに変更を加えることができます。 詳細については、「[フォークの操作](/github/collaborating-with-issues-and-pull-requests/working-with-forks)」を参照してください。

### 他のユーザのプロジェクトへの変更を提案する

たとえば、フォークを使用して、バグの修正に関連する変更を提案できます。 見つけたバグから issue をログに記録するのではなく、以下のことを行えます。

- リポジトリをフォークします。
- 修正する。
- プロジェクトのオーナーにプルリクエストを送信する。

### 他のユーザのプロジェクトを自分のアイディアの出発点として活用する。

オープンソースソフトウェアは、コードを共有することで、より優れた、より信頼性の高いソフトウェアを作成可能にするという考えに基づいています。 詳細については、オープンソース イニシアティブの「[オープンソース イニシアティブについて](https://opensource.org/about)」を参照してください。

{% data variables.product.product_location %} で組織の開発作業にオープンソースの原則を適用する詳細の方法については、{% data variables.product.prodname_dotcom %} のホワイト ペーパー「[InnerSource の概要](https://resources.github.com/whitepapers/introduction-to-innersource/)」を参照してください。

{% ifversion fpt or ghes or ghec %}

他のユーザのプロジェクトのフォークからパブリックリポジトリを作成する際は、プロジェクトの他者との共有方法を定義するライセンスファイルを必ず含めてください。 詳細については、choosealicense.com の「[オープンソース ライセンスの選択](https://choosealicense.com/)」を参照してください。

{% data reusables.open-source.open-source-guide-repositories %} {% data reusables.open-source.open-source-learning %}

{% endif %}

## 前提条件

まだ行っていない場合は、まず [Git を設定する](/articles/set-up-git)必要があります。 [Git から {% data variables.product.product_location %} への認証](/articles/set-up-git#next-steps-authenticating-with-github-from-git)も忘れずに実施してください。

## リポジトリをフォークする

{% webui %}

上流または元のリポジトリへの変更を提案するために、プロジェクトをフォークする場合があります。 この場合、自分のフォークを上流のリポジトリと定期的に同期させるとよいでしょう。 これには、コマンドラインで Git を使用する必要があります。 フォークしたのと同じ [octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) リポジトリを使用して、アップストリーム リポジトリの設定を練習できます。

1. {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom_the_website %}{% else %}{% data variables.product.product_location %}{% endif %} で、[octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) リポジトリに移動します。
2. ページの右上隅の **[フォーク]** を選択します。
   ![[フォーク] ボタン](/assets/images/help/repository/fork_button.png)
3. フォークされたリポジトリの所有者を選びます。
   ![[所有者] ドロップダウンが強調された新しいフォーク ページを作成する](/assets/images/help/repository/fork-choose-owner.png)
4. 既定では、フォークの名前はその親リポジトリと同じです。 フォークの名前を変更して、さらに区別することができます。 
   !["リポジトリ名" フィールドが強調された新しいフォーク ページを作成する](/assets/images/help/repository/fork-choose-repo-name.png)
5. 必要に応じて、リポジトリの説明を追加します。
   !["説明" フィールドが強調された新しいフォーク ページを作成する](/assets/images/help/repository/fork-description.png)
6. 既定のブランチのみをコピーするか、すべてのブランチを新しいフォークにコピーするかを選びます。 オープンソース プロジェクトへのコントリビューションなど、多くのフォーク シナリオでは、既定のブランチのみをコピーする必要があります。 既定では、既定のブランチのみがコピーされます。
   ![既定のブランチのみをコピーするオプション](/assets/images/help/repository/copy-default-branch-only.png)
7. **[フォークの作成]** をクリックします。
   ![強調された [フォークの作成] ボタン](/assets/images/help/repository/fork-create-button.png)


{% note %}

**注:** 親リポジトリから追加のブランチをコピーする場合は、 **[ブランチ]** ページから行うことができます。 詳しくは、「[リポジトリ内でブランチを作成および削除する](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository)」を参照してください。{% endnote %}

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

リポジトリのフォークを作成するには、`gh repo fork` サブコマンドを使用します。

```shell
gh repo fork <em>repository</em>
```

組織内でフォークを作成するには、`--org` フラグを使用します。

```shell
gh repo fork <em>repository</em> --org "octo-org"
```

{% endcli %}

{% desktop %} {% enddesktop %}

## フォークされたリポジトリを複製する

今、Spoon-Knife リポジトリのフォークが存在していますが、お使いのコンピューターのローカルには、そのリポジトリ内のファイルは存在していません。

{% webui %}

1. {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom_the_website %}{% else %}{% data variables.product.product_location %}{% endif %} で、Spoon-Knife リポジトリの **自分のフォーク** に移動します。
{% data reusables.repositories.copy-clone-url %} {% data reusables.command_line.open_the_multi_os_terminal %} {% data reusables.command_line.change-current-directory-clone %}
4. 「`git clone`」と入力し、既にコピーした URL を貼り付けます。 次のようになるはずです。`YOUR-USERNAME` を自分の {% data variables.product.product_name %} のユーザー名に置き換えてください。
  ```shell
  $ git clone https://{% data variables.command_line.codeblock %}/<em>YOUR-USERNAME</em>/Spoon-Knife
  ```

5. **Enter** キーを押します。 これで、ローカルにクローンが作成されます。
  ```shell
  $ git clone https://{% data variables.command_line.codeblock %}/<em>YOUR-USERNAME</em>/Spoon-Knife
  > Cloning into `Spoon-Knife`...
  > remote: Counting objects: 10, done.
  > remote: Compressing objects: 100% (8/8), done.
  > remote: Total 10 (delta 1), reused 10 (delta 1)
  > Unpacking objects: 100% (10/10), done.
  ```

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

フォークのクローンを作成するには、`--clone` フラグを使用します。

```shell
gh repo fork <em>repository</em> --clone=true
```

{% endcli %}

{% desktop %}

{% data reusables.desktop.choose-clone-repository %} {% data reusables.desktop.cloning-location-tab %} {% data reusables.desktop.cloning-repository-list %} {% data reusables.desktop.choose-local-path %} {% data reusables.desktop.click-clone %}

{% enddesktop %}

## フォークが元のリポジトリと同期するように Git を構成する

プロジェクトをフォークして元のリポジトリへの変更を提案する場合は、Git を構成することで、元のリポジトリまたは上流のリポジトリからフォークのローカルのクローンへ変更をプルできます。

{% webui %}

1. {% ifversion fpt or ghec %}{% data variables.product.prodname_dotcom_the_website %}{% else %}{% data variables.product.product_location %}{% endif %} で、[octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) リポジトリに移動します。
{% data reusables.repositories.copy-clone-url %} {% data reusables.command_line.open_the_multi_os_terminal %}
4. 複製したフォークの場所にディレクトリを変更します。
    - ホーム ディレクトリに移動するには、他のテキストを含めずに「`cd`」と入力します。
    - 現在のディレクトリのファイルとフォルダーを一覧表示するには、「`ls`」と入力します。
    - 一覧表示されているディレクトリのいずれかに移動するには、「`cd your_listed_directory`」と入力します。
    - 1 つ上のディレクトリに移動するには、「`cd ..`」と入力します。
5. 「`git remote -v`」と入力して **Enter** キーを押します。 フォーク用に現在構成されているリモート リポジトリが表示されます。
  ```shell
  $ git remote -v
  > origin  https://{% data variables.command_line.codeblock %}/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (fetch)
  > origin  https://{% data variables.command_line.codeblock %}/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (push)
  ```

6. 「`git remote add upstream`」と入力し、手順 3 でコピーした URL を貼り付け、**Enter キー** を押します。 次のようになります。
  ```shell
  $ git remote add upstream https://{% data variables.command_line.codeblock %}/ORIGINAL_OWNER/Spoon-Knife.git
  ```

7. フォーク用に指定した新しい上流リポジトリを検証するには、再度「`git remote -v`」と入力します。 フォークの URL は `origin` のように表示され、元のリポジトリの URL は `upstream` のように表示されます。
  ```shell
  $ git remote -v
  > origin    https://{% data variables.command_line.codeblock %}/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (fetch)
  > origin    https://{% data variables.command_line.codeblock %}/<em>YOUR_USERNAME</em>/<em>YOUR_FORK</em>.git (push)
  > upstream  https://{% data variables.command_line.codeblock %}/<em>ORIGINAL_OWNER</em>/<em>ORIGINAL_REPOSITORY</em>.git (fetch)
  > upstream  https://{% data variables.command_line.codeblock %}/<em>ORIGINAL_OWNER</em>/<em>ORIGINAL_REPOSITORY</em>.git (push)
  ```

これで、いくつかの Git コマンドでフォークと上流リポジトリの同期を維持できます。 詳細については、「[フォークの同期](/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork)」を参照してください。

{% endwebui %}

{% cli %}

{% data reusables.cli.cli-learn-more %}

フォークされたリポジトリのリモート リポジトリを構成するには、`--remote` フラグを使用します。

```shell
gh repo fork <em>repository</em> --remote=true
```

リモート リポジトリの名前を指定するには、`--remote-name` フラグを使用します。

```shell
gh repo fork <em>repository</em> --remote-name "main-remote-repo"
```

{% endcli %}

### フォークを編集する

フォークには、次のような変更を加えることができます。

- **ブランチの作成:** [*ブランチ*](/articles/creating-and-deleting-branches-within-your-repository/) を使用すると、メイン プロジェクトを危険にさらすことなく、新しい機能を構築し、アイデアをテストできます。
- **pull request を開く:** 元のリポジトリに投稿する場合は、[pull request](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) を送信することで、フォークをリポジトリにプルする要求を元の作成者に送信できます。

## フォークする他のリポジトリを見つける
リポジトリをフォークしてプロジェクトへのコントリビューションを開始しましょう。 {% data reusables.repositories.you-can-fork %}

{% ifversion fpt or ghec %}[[探索]](https://github.com/explore) を参照すると、プロジェクトを検索し、オープンソース リポジトリへの投稿を開始できます。 詳細については、「[{% data variables.product.prodname_dotcom %} でオープンソースに貢献する方法を見つける](/github/getting-started-with-github/finding-ways-to-contribute-to-open-source-on-github)」を参照してください。

{% endif %}

## 次の手順

リポジトリをフォークし、フォークのクローンを練習し、上流リポジトリを構成しました。

* フォークを複製し、コンピューターからフォークしたリポジトリの変更を同期する方法の詳細については、「[Git のセットアップ](/articles/set-up-git)」を参照してください。

* 新しいリポジトリを作成して、すべてのプロジェクトを配置し、コードを {% data variables.product.prodname_dotcom %} で共有することもできます。 {% data reusables.getting-started.create-a-repository %}"

* {% data reusables.getting-started.being-social %}

* {% data reusables.support.connect-in-the-forum-bootcamp %}
