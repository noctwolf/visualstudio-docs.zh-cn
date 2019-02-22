---
title: 如何：配置计算机以开发 Office 解决方案
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- prerequisites [Office development in Visual Studio]
- Office development in Visual Studio, installing tools
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ff441de5d3643a1c8c4e9b57a98c7a5563d1ea62
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56653965"
---
# <a name="how-to-configure-a-computer-to-develop-office-solutions"></a>如何：配置计算机以开发 Office 解决方案
  若要配置开发计算机以便可以使用 Visual Studio 中的 Microsoft Office 开发人员工具，请按照本主题中的说明进行操作。 必须在本地计算机上具有管理特权才能执行这些步骤。

### <a name="to-configure-the-development-computer"></a>配置开发计算机

1.  安装包括 Office 开发人员工具的 Visual Studio 版本。 默认安装 Office 开发人员工具。 如果您通过选择要安装的功能来自定义 Visual Studio 安装，请确保**Microsoft Office Developer Tools**安装过程中选择。 有关包括 Office 开发人员工具的 Visual Studio 版本的详细信息，请参阅[配置计算机以开发 Office 解决方案](../vsto/configuring-a-computer-to-develop-office-solutions.md)。

2.  安装 Visual Studio 中的 Office 开发人员工具支持的 Office 的版本。 有关详细信息，请参阅[配置计算机以开发 Office 解决方案](../vsto/configuring-a-computer-to-develop-office-solutions.md)。

     请确保也为安装的 Office 版本安装的 PIA。 默认情况下，PIA 随 Office 一起安装。 如果修改 Office 安装程序，请确保 **.NET 可编程性支持**功能选择想要面向的应用程序。

3.  如果您有英语版本的 Visual Studio，但对 Windows 使用非英语设置，则可以安装[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]语言包以查看[!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]与 Windows 相同的语言中的消息。 Visual Studio 的非英语版本将自动安装该语言包。 语言包是可从[Microsoft 下载中心](http://go.microsoft.com/fwlink/?LinkId=140386)。

## <a name="see-also"></a>请参阅
- [什么是中的 Office 开发的新增功能](https://msdn.microsoft.com/bf054af2-c896-4723-aa15-6381145b14bb)
- [开始&#40;Visual Studio 中的 Office 开发&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [如何：安装 Visual Studio Tools for Office runtime 可再发行组件](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [如何：安装 Office 主互操作程序集](../vsto/how-to-install-office-primary-interop-assemblies.md)
