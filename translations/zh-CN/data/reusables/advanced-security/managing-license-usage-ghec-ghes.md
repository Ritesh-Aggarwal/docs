---
ms.openlocfilehash: c47a4efc23963dcfa0be69207387cd2d02704aef
ms.sourcegitcommit: 47bd0e48c7dba1dde49baff60bc1eddc91ab10c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2022
ms.locfileid: "145098394"
---
为仓库启用或禁用 {% data variables.product.prodname_advanced_security %} 时，{% data variables.product.prodname_dotcom %} 将显示许可证使用情况变化的概况。 如果您禁用对 {% data variables.product.prodname_GH_advanced_security %} 的访问，任何被“唯一”提交者使用的席位都将释放。

如果您超过了许可证限制，{% data variables.product.prodname_GH_advanced_security %} 将继续在所有已启用的仓库中工作。 但是，在为新仓库启用 {% data variables.product.prodname_GH_advanced_security %} 的组织中，将会创建禁用该功能的仓库。 此外，对现有存储库启用 {% data variables.product.prodname_GH_advanced_security %} 的选项将不可用。{% ifversion fpt or ghec %} 如果将公共存储库的可见性更改为专用，则 {% data variables.product.prodname_GH_advanced_security %} 将对该存储库禁用。{% endif %}

一旦您释放一些席位，通过对某些仓库禁用 {% data variables.product.prodname_GH_advanced_security %} 或通过增加您的许可证大小，用于启用 {% data variables.product.prodname_GH_advanced_security %} 的选项将继续正常工作。
