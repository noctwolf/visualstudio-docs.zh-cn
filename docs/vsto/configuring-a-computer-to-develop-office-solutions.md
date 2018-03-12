---
title: "配置计算机以开发 Office 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, installing tools
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 9b63b3b495b9cb15ea3e9eeedcecedb3a384f8a0
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="configuring-a-computer-to-develop-office-solutions"></a>将计算机配置为开发 Office 解决方案

若要为 Microsoft Office 创建 VSTO 外接程序和自定义项，请安装 Visual Studio、.NET Framework 和 Microsoft Office 的受支持版本。

|软件|受支持的版本|
|--------------|------------------------|
|Visual Studio 2017| 与任何版本**Office/SharePoint 开发**工作负荷。|
|.NET Framework|-.NET Framework 4 或更高版本。|
|Microsoft Office|<ul><li>任何 Office 套件版本，包括 Office Professional Plus for Office 365。</li><li>以下任一独立应用程序：<br /><br /> <ul><li>Excel</li><li>InfoPath（仅 Office 2013 和 Office 2010）</li><li>Outlook</li><li>PowerPoint</li><li>项目</li><li>Visio</li><li>Word</li></ul></li></ul><br /> Visual Basic for Applications (VBA) 必须作为 Office 的一部分安装。 **重要说明：**不支持 Office 2010 应用程序的即点即用版本。|

有关详细的安装步骤，请参阅[如何： 配置计算机以开发 Office 解决方案](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)。

## <a name="if-project-templates-dont-appear-or-they-dont-work-in-visual-studio"></a>如果项目模板不显示，或它们不适用于 Visual Studio 中

如果你安装受支持的版本的 Visual Studio、.NET Framework 和 Microsoft Office，但是 Office 项目模板不显示在 Visual Studio**新项目**对话框中，或者你收到错误，当你尝试使用其中一个，检查下列项目：

- 确保你已经在计算机上安装了 Microsoft Office 开发人员工具。

     Office 开发人员工具是 Visual Studio 的可选组件，但是它们通常随 Visual Studio 一起自动安装。 如果通过指定要安装的功能来自定义 Visual Studio 安装，请在安装过程中选择 **“Microsoft Office 开发人员工具”** 来安装这些工具。

     若要确保安装这些工具，启动 Visual Studio 安装程序，并选择**修改**按钮。 选中 **“Microsoft Office 开发人员工具”** 复选框，然后选择 **“更新”** 按钮。

- 请确保你不运行的提供通过单击运行的 Office 版本。 请参阅 [如何：验证 Outlook 是否是计算机上的“即点即用”应用程序](http://msdn.microsoft.com/library/office/ff864733(v=office.14).aspx)。

- 确保运行只有一个版本的 Microsoft Office。

如果你继续遇到问题，请参阅 [Additional Support for Errors in Office Solutions](../vsto/additional-support-for-errors-in-office-solutions.md)。

## <a name="see-also"></a>请参阅

[入门 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/getting-started-office-development-in-visual-studio.md)  
[如何：将计算机配置为开发 Office 解决方案](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)  
[如何：安装 Visual Studio Tools for Office 运行时可再发行组件](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)  
[如何：安装 Office 主互操作程序集](../vsto/how-to-install-office-primary-interop-assemblies.md)  
[按 Office 应用程序和项目类型提供的功能](../vsto/features-available-by-office-application-and-project-type.md)
