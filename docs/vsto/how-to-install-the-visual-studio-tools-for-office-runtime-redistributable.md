---
title: 如何：安装 Visual Studio Tools for Office runtime 可再发行组件
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio]
- installing Office development tools in Visual Studio
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 205fb184997130423072d556a60e1323a99e6ad8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101452"
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>如何：安装 Visual Studio Tools for Office runtime 可再发行组件
  必须在运行使用 Microsoft Office 开发人员工具中的创建的解决方案，每台计算机上安装 Visual Studio 2010 Tools for Office 运行时[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]。 安装 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 和 Microsoft Office 时会自动安装运行时。 有关详细信息，请参阅[Visual Studio Tools for Office runtime 安装方案](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)。

 在以下情况，你可能需要按照手动安装说明操作：

- 需要在服务器上安装 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 例如，希望使用 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 类来管理服务器上的文档级解决方案。

- 需要在已安装 Office 解决方案的所有其他先决条件的计算机上安装运行时。

    > [!NOTE]
    >  若要安装 .NET Framework 和 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]，你必须是开发计算机上的管理员。

## <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>安装 Visual Studio Tools for Office runtime

1. 安装 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 或更高版本。

    - 若要下载[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]，请参阅[Microsoft.NET Framework 4 （Web 安装程序）](http://go.microsoft.com/fwlink/?LinkId=178957)。

    - 若要下载[!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)]，请参阅[Microsoft.NET Framework 4 Client Profile （Web 安装程序）](http://go.microsoft.com/fwlink/?LinkId=178958)。

    - 若要下载[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]，请参阅[Microsoft.NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653)。

2. 运行*vstor_redist.exe*安装[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。

     您可以下载这些安装程序郎[Visual Studio 2010 Tools for Office 运行时](http://go.microsoft.com/fwlink/?LinkId=140384)。 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 的先决条件与 .NET Framework 的先决条件相匹配。

     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 包括语言包。 如果 Windows 安装设置为非英语语言，则可以以 Windows 使用的语言显示运行时消息。 同样，如果最终用户安装 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]，然后在设置为非英语语言的 Windows 安装上运行你的解决方案，则运行时消息将以与 Windows 相同的语言显示。 在某些情况下，可能需要其他语言包。 例如，可能需要其他语言包，如果您的 Windows 副本使用多个语言设置，或已安装后切换到另一种语言[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]。 您可以找到的语言包[Microsoft Visual Studio 2010 Tools，供 Microsoft Office system （版本 4.0 运行时） 语言包](http://go.microsoft.com/fwlink/?LinkId=140386)。

## <a name="see-also"></a>请参阅
- [开始&#40;Visual Studio 中的 Office 开发&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [配置计算机以开发 Office 解决方案](../vsto/configuring-a-computer-to-develop-office-solutions.md)
- [如何：配置计算机以开发 Office 解决方案](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [如何：安装 Office 主互操作程序集](../vsto/how-to-install-office-primary-interop-assemblies.md)
- [使用 ServerDocument 类管理服务器上的文档](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)
- [部署 Office 解决方案](../vsto/deploying-an-office-solution.md)
