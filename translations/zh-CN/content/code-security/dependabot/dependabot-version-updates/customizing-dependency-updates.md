---
title: 自定义依赖项更新
intro: '您可以自定义 {% data variables.product.prodname_dependabot %} 如何维护依赖项。'
permissions: 'People with write permissions to a repository can configure {% data variables.product.prodname_dependabot %} for the repository.'
redirect_from:
  - /github/administering-a-repository/customizing-dependency-updates
  - /code-security/supply-chain-security/customizing-dependency-updates
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/customizing-dependency-updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '>3.2'
type: how_to
topics:
  - Dependabot
  - Version updates
  - Security updates
  - Repositories
  - Dependencies
  - Pull requests
  - Vulnerabilities
shortTitle: Customize updates
ms.openlocfilehash: 6cb6db974fe880bccc76c89447dc077e0617df9a
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145101104'
---
{% data reusables.dependabot.beta-security-and-version-updates %} {% data reusables.dependabot.enterprise-enable-dependabot %}

## 关于自定义依赖项更新

启用版本更新后，可以通过向 dependabot.yml 文件添加更多选项来自定义 {% data variables.product.prodname_dependabot %} 维护依赖项的方式。 例如，可以：

- 指定星期几打开版本更新的拉取请求：`schedule.day`
- 为每个包管理器设置审阅者、被分派人和标签：`reviewers`、`assignees` 和 `labels`
- 为每个清单文件的更改定义版本控制策略：`versioning-strategy`
- 更改为版本更新打开的最大拉取请求数（默认值为 5）：`open-pull-requests-limit`
- 打开版本更新的拉取请求以定位特定分支，而不是默认分支：`target-branch`

有关配置选项的详细信息，请参阅“[dependabot.yml 文件的配置选项](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/configuration-options-for-dependency-updates)”。

更新存储库中的 dependabot.yml 文件后，{% data variables.product.prodname_dependabot %} 会使用新配置即刻进行检查。 几分钟内，你将在 {% data variables.product.prodname_dependabot %} 选项卡上看到更新的依赖项列表，如果存储库有很多依赖项，可能需要更长时间。 您可能还会看到针对版本更新的新拉取请求。 有关详细信息，请参阅“[列出为版本更新配置的依赖项](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/listing-dependencies-configured-for-version-updates)”。

## 配置更改对安全更新的影响

如果自定义 dependabot.yml 文件，可能会注意到针对安全更新提出的拉取请求发生了一些变化。 这些拉取请求始终由依赖项的安全通告触发，而不是由 {% data variables.product.prodname_dependabot %} 时间表触发。 但是，它们会从 dependabot.yml 文件继承相关的配置设置，除非为版本更新指定不同的目标分支。

有关示例，请参阅下面的“[设置自定义标签](#setting-custom-labels)”。

## 修改计划

设置 `daily` 更新计划后，{% data variables.product.prodname_dependabot %} 会默认在 05:00 UTC 检查新版本。 可以使用 `schedule.time` 指定检查更新的备用时间（格式：`hh:mm`）。

下面的示例 dependabot.yml 文件扩展了 npm 配置，以指定 {% data variables.product.prodname_dependabot %} 应何时检查依赖项的版本更新。

```yaml
# dependabot.yml file with
# customized schedule for version updates

version: 2
updates:
  # Keep npm dependencies up to date
  - package-ecosystem: "npm"
    directory: "/"
    # Check the npm registry for updates at 2am UTC
    schedule:
      interval: "daily"
      time: "02:00"
```

## 设置审查者和受理人

默认情况下，{% data variables.product.prodname_dependabot %} 会提出没有任何审查者或受理人的拉取请求。

可以使用 `reviewers` 和 `assignees` 为针对包管理器提出的所有拉取请求指定审阅者和被分派人。 指定一个团队时，必须使用完整的团队名称，就像 @mentioning 团队（包括组织）一样。

下面的示例 dependabot.yml 文件更改了 npm 配置，使所有通过 npm 的版本和安全更新打开的拉取请求都有两个审阅者和一个被分派人。

```yaml
# dependabot.yml file with
# reviews and an assignee for all npm pull requests

version: 2
updates:
  # Keep npm dependencies up to date
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "daily"
    # Raise all npm pull requests with reviewers
    reviewers:
      - "my-org/team-name"
      - "octocat"
    # Raise all npm pull requests with an assignee
    assignees:
      - "user-name"
```

## 设置自定义标签

{% data reusables.dependabot.default-labels %}

可以使用 `labels` 替代默认标签，并为针对包管理器提出的所有拉取请求指定替代标签。 无法在 dependabot.yml 文件中创建新标签，因此，存储库中必须已存在替代标签。

下面的示例 dependabot.yml 文件更改了 npm 配置，使所有通过 npm 的版本和安全更新打开的拉取请求都有自定义标签。 它还会更改 Docker 配置，以针对自定义分支检查版本更新，并针对自定义分支使用自定义标签提出拉取请求。 Docker 的变更不会影响安全更新拉取请求，因为安全更新始终针对默认分支进行。

{% note %}

只有：新版 `target-branch` 必须包含要更新的 Dockerfile，，此变更将导致 Docker 版本更新被禁用。

{% endnote %}

```yaml
# dependabot.yml file with
# customized npm configuration

version: 2
updates:
  # Keep npm dependencies up to date
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "daily"
    # Raise all npm pull requests with custom labels
    labels:
      - "npm dependencies"
      - "triage-board"

    # Keep Docker dependencies up to date
  - package-ecosystem: "docker"
    directory: "/"
    schedule:
      interval: "daily"
    # Raise pull requests for Docker version updates
    # against the "develop" branch. The Docker configuration
    # no longer affects security update pull requests.
    target-branch: "develop"
    # Use custom labels on pull requests for Docker version updates
    labels:
      - "Docker dependencies"
      - "triage-board"
```

## 更多示例

有关详细信息，请参阅“[dependabot.yml 文件的配置选项](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/configuration-options-for-dependency-updates)”。
