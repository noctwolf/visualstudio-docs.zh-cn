---
title: "管理应用程序资源 (.NET) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- editors [Visual Studio], Resource Designer
- Resource Designer
- resources [Visual Studio], managing
- Resources page in Project Designer
- resources types, Resource Designer
- application resources [Visual Studio]
- Project Designer, Resources page
ms.assetid: f2582734-8ada-4baa-8a7c-e2ef943ddf7e
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b599a919911fcc5d2833cfe69b75f7b32cced858
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="managing-application-resources-net"></a>管理应用程序资源 (.NET)
资源文件是应用程序使用的不可编译的文件，例如图标文件或音频文件。 由于这些文件不是编译过程的一部分，因此你可以更改它们而无需重新编译二进制文件。 如果打算本地化你的应用程序，则应为本地化应用程序时需要进行更改的所有字符串和其他资源使用资源文件。  
  
有关 .NET 桌面应用中的资源的详细信息，请参阅 [Resources in Desktop Apps](/dotnet/framework/resources/index)。 有关 C++ 桌面应用中的资源的详细信息，请参阅 [Working with Resource Files](/cpp/windows/working-with-resource-files)。  
  
UWP 应用使用的资源模型与桌面应用不同。 有关 Windows 8.x 应用中资源的信息，请参阅[定义应用资源 (HTML)](https://msdn.microsoft.com/en-us/library/windows/apps/hh465228.aspx)。  
  
## <a name="working-with-resources"></a>使用资源  
在托管代码项目中，打开项目属性窗口。 可通过以下任一方法来打开属性窗口：

- 右键单击“解决方案资源管理器”中的项目节点，并选择“属性”
- 在“快速启动”窗口的“项目属性”中键入属性
- 在“解决方案资源管理器”窗口中，选择 Alt + Enter

选择“资源”  选项卡。如果你的项目尚未包含 .resx 文件，你可以添加一个，添加和删除不同类型的资源，并修改现有资源。  
  
若要了解如何使用 C++ 项目中的资源，请参阅 [How to: Create a Resource](/cpp/windows/how-to-create-a-resource)。