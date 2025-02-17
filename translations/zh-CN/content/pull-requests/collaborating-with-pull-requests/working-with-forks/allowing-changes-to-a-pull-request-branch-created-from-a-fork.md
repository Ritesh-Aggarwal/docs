---
title: 允许更改从复刻创建的拉取请求分支
intro: 为增强协作，可以允许在你从自己个人帐户拥有的分支所创建的分支上提交。
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/working-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork
  - /articles/allowing-changes-to-a-pull-request-branch-created-from-a-fork
  - /github/collaborating-with-issues-and-pull-requests/allowing-changes-to-a-pull-request-branch-created-from-a-fork
  - /github/collaborating-with-pull-requests/working-with-forks/allowing-changes-to-a-pull-request-branch-created-from-a-fork
permissions: People with push access to the upstream repository of a fork owned by a personal account can commit to the forked branches.
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
shortTitle: Allow changes to a branch
ms.openlocfilehash: 26255f5aeab3bcaa5ecc1aa6cf865981990c456a
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145129986'
---
只有拉取请求作者才可授权上游仓库维护员或对上游仓库具有推送权限的人员，允许他们提交到用户拥有的复刻中其拉取请求的比较分支。 若要了解有关上游存储库的详细信息，请参阅“[关于分支](/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks)”。

拉取请求作者可在最初从用户拥有的复刻创建拉取请求时或在创建拉取请求后授予这些权限。 有关详细信息，请参阅“[从分支创建拉取请求](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)”。

您可以在第一次从复刻创建拉取请求时设置提交权限。 有关详细信息，请参阅“[从分支创建拉取请求](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork)”。 此外，您也可以修改现有拉取请求，让仓库维护员提交到分支。

## 在现有拉取请求上启用仓库维护员权限

1. 在 {% data variables.product.product_name %} 上，导航到拉取请求上游仓库的主页面。
2. 在上游存储库名称下，单击 {% octicon "git-pull-request" aria-label="The pull request icon" %}“拉取请求”。
![问题和拉取请求选项卡选择](/assets/images/help/repository/repo-tabs-pull-requests.png)
3. 在拉取请求列表中，导航到要允许在其中提交的拉取请求。
{% data reusables.repositories.allow-maintainers-user-forks %}

  ![allow-maintainers-to-make-edits-sidebar-checkbox](/assets/images/help/pull_requests/allow-maintainers-to-make-edits-sidebar-checkbox.png)

## 延伸阅读

- [将更改提交到从分支创建的拉取请求分支](/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/committing-changes-to-a-pull-request-branch-created-from-a-fork)
