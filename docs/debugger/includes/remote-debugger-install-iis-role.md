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
ms.openlocfilehash: 62bdcd8109263cc86e13484d146e46f8e95c7198
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
这些步骤演示了基本配置的 IIS。 有关详细信息或要安装到 Windows 桌面计算机，请参阅[发布到 IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)或[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

对于 Windows Server 操作系统，使用**添加角色和功能**向导通过**管理**链接或**仪表板**中链接**服务器管理器**. 在“服务器角色”步骤中，选中“Web 服务器(IIS)”框。

![在选择服务器角色步骤中选择了“Web 服务器 IIS”角色。](../media/remotedbg-server-roles-ws2012.png)

在“角色服务”步骤中，选择所需 IIS 角色服务，或接受提供的默认角色服务。 如果你计划部署使用 Web 部署，请确保**IIS 管理脚本和工具**选择。

继续完成安装的 web 服务器角色和服务的确认步骤。 安装 Web 服务器 (IIS) 角色后无需重启服务器/IIS。