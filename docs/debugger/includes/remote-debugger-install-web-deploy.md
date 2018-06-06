---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: c22ba73b464f91bf3036541304cdf94e8660970d
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794195"
---
1. 如果你想要使用 Web 部署 Visual Studio 中部署应用程序，请在服务器上安装 Web 部署的最新版本。

    若要安装 Web 部署，使用[Web 平台安装程序 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)。 (若要查找从 IIS 的 Web 平台安装程序链接，选择**IIS**在左窗格中的服务器管理器中。 右键单击服务器并选择**Internet Information Services (IIS) Manager**。)

    在 Web 平台安装程序中，你找到 Web 部署的应用程序选项卡中。你还可以获取直接从安装程序[Microsoft Download Center](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc)。 

2. 验证 Web 部署正在运行正确通过打开**控制面板 > 系统和安全 > 管理工具 > 服务**并确保**Web 部署代理服务**正在运行 (服务名称是在旧版本不同）。

    如果代理服务未运行，则启动它。 如果它根本不存在，请转到**控制面板 > 程序 > 卸载程序**，查找**Microsoft Web Deploy <version>** 。 选择**更改**安装，并确保你选择**将安装到本地硬盘**Web 部署组件。 完成更改安装步骤。