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
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38811910"
---
1. 如果你想要使用 Web 部署在 Visual Studio 中部署应用程序，请在服务器上安装最新版本的 Web 部署。

    若要安装 Web 部署，请使用[Web 平台安装程序 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)。 (若要查找从 IIS 的 Web 平台安装程序链接，请选择**IIS**服务器管理器的左窗格中。 右键单击服务器，然后选择**Internet 信息服务 (IIS) 管理器**。)

    在 Web 平台安装程序，您发现 Web 部署的应用程序选项卡中。你还可以获取直接从安装程序[Microsoft Download Center](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc)。 

2. 验证，Web 部署是否正常运行通过打开**控制面板 > 系统和安全性 > 管理工具 > 服务**并确保选中**Web 部署代理服务**正在运行 (服务名称是在旧版本）。

    如果代理服务未运行，启动它。 如果它根本不存在，请转到**控制面板 > 程序 > 卸载程序**，找到**Microsoft Web Deploy <version>** 。 选择**更改**安装，并确保你选择**将安装到本地硬盘驱动器**Web 部署组件。 完成更改安装步骤。