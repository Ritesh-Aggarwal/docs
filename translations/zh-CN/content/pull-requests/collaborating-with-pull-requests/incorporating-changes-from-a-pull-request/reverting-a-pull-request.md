---
title: 还原拉取请求
intro: 您可以在将拉取请求合并到上游分支后进行还原。
redirect_from:
  - /github/collaborating-with-issues-and-pull-requests/incorporating-changes-from-a-pull-request/reverting-a-pull-request
  - /github/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/reverting-a-pull-request
  - /articles/reverting-a-pull-request
  - /github/collaborating-with-issues-and-pull-requests/reverting-a-pull-request
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Pull requests
ms.openlocfilehash: 9e94b6e9358089da8f62ff5152800e14556db3e7
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145130107'
---
## 关于还原拉取请求

在 {% data variables.product.product_name %} 上还原拉取请求会创建一个新拉取请求。其中包含原始合并拉取请求中一个还原的合并提交。 若要还原拉取请求，必须在存储库中拥有[写入权限](/organizations/managing-access-to-your-organizations-repositories/repository-roles-for-an-organization)。 

## 还原拉取请求

{% note %}

注意：如果以下任一内容属实，你可能需要还原拉取请求中的单个提交。

- 还原拉取请求导致合并冲突
- 原始拉取请求最初在 {% data variables.product.product_name %} 上未合并。 例如，有人可能已在命令行上使用快进合并来合并拉取请求。

有关使用 Git 手动还原单个提交的详细信息，请参阅 Git 文档中的 [Git 还原](https://git-scm.com/docs/git-revert.html)。

{% endnote %}

{% data reusables.repositories.sidebar-pr %}
2. 在“Pull Requests（拉取请求）”列表中，单击要还原的拉取请求。
3. 在拉取请求底部附近，单击“还原”。 如果未显示“还原”选项，则需要请求存储库管理员授予写入权限。
  ![还原拉取请求链接](/assets/images/help/pull_requests/revert-pull-request-link.png)
4. 合并产生的拉取请求。 有关详细信息，请参阅“[合并拉取请求](/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)”。
