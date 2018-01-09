---
title: "项目和解决方案文件类型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- File Properties.CopyToOutputDirectory
- File Properties.CustomToolNamespace
- File Properties.FileName
- File Properties.FullPath
- File Properties.BuildAction
- File Properties.CustomTool
- FileProperties
helpviewer_keywords:
- .sln files
- .suo files
- file types [Visual Studio]
- file extensions [Visual Studio]
- solution files [Visual Studio]
- sln files
- suo files
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d05b7b5f1510777c758998572e78757c47148fa1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="project-and-solution-file-types"></a>项目和解决方案文件类型

Visual Studio 支持许多文件类型。 在特定安装中，已安装的组件确定哪些文件类型受支持。 本主题列出某些典型安装中支持的解决方案和项目文件类型。

## <a name="solution-files-sln-and-suo"></a>解决方案文件（.sln 和 .suo）

Visual Studio 采用两种文件类型（.sln 和 .suo）来存储解决方案设置。 这些文件总称为解决方案文件，为解决方案资源管理器提供显示管理文件的图形接口所需的信息。

|扩展名|名称|描述|
|---------------|----------|-----------------|
|.sln|Visual Studio 解决方案|将项目、项目项和解决方案项组织到解决方案中。|
|.suo|解决方案用户选项|跟踪对 Visual Studio 所做的用户级自定义，如断点。|

## <a name="project-files"></a>项目文件

项目可以包含许多不同的文件类型。 例如，C# 代码文件的扩展名为 .cs，而 C++ 文件的扩展名为 .cpp。 资源存储在 .resx 文件中，XAML 存储在 .xaml 文件中。 [App.config](../../ide/managing-application-settings-dotnet.md) 文件包含不应包含在应用程序代码中的应用程序信息 &mdash; 例如连接字符串。

有关 C++ 项目中文件类型的详细信息，请参阅[为 Visual C++ 项目创建的文件类型](/cpp/ide/file-types-created-for-visual-cpp-projects)和 [Microsoft 基础类库中的 Unicode](/cpp/mfc/unicode-in-mfc)

## <a name="see-also"></a>请参阅

[解决方案和项目](../../ide/solutions-and-projects-in-visual-studio.md)