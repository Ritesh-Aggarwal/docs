---
title: 测试应用程序
intro: 'GitHub 建议在将上架信息提交到 {% data variables.product.prodname_marketplace %} 之前，先使用 API 和 web 挂钩测试您的应用，以便为客户提供理想的体验。 在上架专家批准您的应用程序之前，它必须能够完全处理帐单流程。'
redirect_from:
  - /apps/marketplace/testing-apps-apis-and-webhooks
  - /apps/marketplace/integrating-with-the-github-marketplace-api/testing-github-marketplace-apps
  - /marketplace/integrating-with-the-github-marketplace-api/testing-github-marketplace-apps
  - /developers/github-marketplace/testing-your-app
versions:
  fpt: '*'
  ghec: '*'
topics:
  - Marketplace
ms.openlocfilehash: c542f5bd46e4555a4459c669e2f9d75e29b63ffe
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: '145098015'
---
## 测试应用程序

您可以使用 {% data variables.product.prodname_marketplace %} 上架草稿来模拟每个帐单流程。 上架信息处于草稿状态意味着它尚未提交以供审批。 使用 {% data variables.product.prodname_marketplace %} 草拟列表进行的任何购买都不会产生真正的交易，GitHub 不会从信用卡中扣款。 请注意，您只能模拟在列表草案中公布的计划的购买情况，而不能模拟计划草案中的购买情况。 有关详细信息，请参阅“[为应用草拟列表](/developers/github-marketplace/drafting-a-listing-for-your-app)”和“[在应用中使用 {% data variables.product.prodname_marketplace %} API](/developers/github-marketplace/using-the-github-marketplace-api-in-your-app)”。

### 使用带有上架草稿的开发应用程序来测试更改

{% data variables.product.prodname_marketplace %} 上架信息只能与单个应用程序注册相关联，并且每个应用程序只能访问它自己的 {% data variables.product.prodname_marketplace %} 上架信息。 出于这些原因，我们建议配置一个与生产应用程序配置相同的单独的开发应用程序，并创建可用于测试的 {% data variables.product.prodname_marketplace %} 草拟列表。 {% data variables.product.prodname_marketplace %} 草稿允许您测试更改而不影响生产应用程序的活动用户。 您无需提交开发 {% data variables.product.prodname_marketplace %} 上架信息，因为它仅用于测试。

由于只能为公共应用程序创建 {% data variables.product.prodname_marketplace %} 上架草稿，因此您必须将开发应用程序设为公共。 公共应用程序不会在已发布的 {% data variables.product.prodname_marketplace %} 上架信息之外被发现，只要您不分享该应用程序的 URL。 处于草稿状态的 Marketplace 上架信息仅对应用程序的所有者可见。

一旦有了带有上架草稿的开发应用程序，就可以在与 {% data variables.product.prodname_marketplace %} API 和 web 挂钩集成的同时，使用它来测试您对应用程序所做的更改。

{% warning %}

不要使用 {% data variables.product.prodname_marketplace %} 中上线的应用程序来测试购买。

{% endwarning %}

### 模拟 Marketplace 购买事件

您的测试场景可能需要设置可提供免费试用并且可在免费和付费订阅之间切换的上架计划。 由于降级和取消要到下一个结算周期才会生效，因此 GitHub 提供一个开发人员专用功能“应用待处理更改”，以强制 `changed` 和 `cancelled` 计划操作立即生效。 对于带有 Marketplace 草拟列表的应用，可以在 https://github.com/settings/billing#pending-cycle: 中访问“应用待处理更改”

![应用待处理更改](/assets/images/github-apps/github-apps-apply-pending-changes.png)

## 测试 API

对于大多数 {% data variables.product.prodname_marketplace %} API 端点，我们还提供存根 API 端点，它们返回可用于测试的硬编码假数据。 若要接收存根数据，必须指定存根 URL，其路由中包括 `/stubbed`（例如，`/user/marketplace_purchases/stubbed`）。 有关支持此存根数据方法的终结点的列表，请参阅 [{% data variables.product.prodname_marketplace %} 终结点](/rest/reference/apps#github-marketplace)。

## 测试 web 挂钩

GitHub 提供用于测试已部署有效负载的工具。 有关详细信息，请参阅“[测试 Webhook](/webhooks/testing/)”。
