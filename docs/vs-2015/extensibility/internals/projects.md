---
title: 项目 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- solutions [Visual Studio]
- custom tools [Visual Studio SDK]
- project subtypes [Visual Studio SDK]
- projects [Visual Studio SDK]
- project types [Visual Studio SDK]
ms.assetid: 237742e4-a638-4d5b-a9b3-6a69d627763c
caps.latest.revision: 44
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ade0234423c907c675bc1dd53e3436dfa38ca26e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469822"
---
# <a name="projects"></a>项目
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[项目](https://docs.microsoft.com/visualstudio/extensibility/internals/projects)。  
  
在 Visual Studio 中，项目是开发人员用于组织源代码文件和显示在其他资源的容器**解决方案资源管理器**。 通常情况下，项目是存储对源代码文件和资源，如位图文件的引用的文件 （例如，对于 C# 项目的.csproj 文件）。 项目的让组织、 生成、 调试和部署的源代码，请对 Web 服务和数据库，以及其他资源的引用。 Vspackage 可以扩展 Visual Studio 项目系统在三个方面：*项目类型*，*项目子类型*，并*自定义工具*。  
  
## <a name="in-this-section"></a>本节内容  
 [项目类型](../../extensibility/internals/project-types.md)  
 *项目类型*添加对新类型的项目，例如编程语言的支持。 例如，Visual Studio 支持每种语言有其自己的项目类型，并且 IronPython 集成示例包括 IronPython 语言的项目类型。 必须创建 C# 或 Visual Basic 自定义如何项将生成、 调试、 部署，并显示在非语言的项目类型**解决方案资源管理器**。 有关详细信息，请参阅[项目类型](../../extensibility/internals/project-types.md)。  
  
 [项目子类型](../../extensibility/internals/project-subtypes.md)  
 *项目子类型*基于项目类型，可用于自定义生成、 调试和部署项目的方式。 Visual Studio 使用项目子类型用于智能设备项目;它们通过将新生成的程序从开发计算机复制到目标设备自定义部署。 C# 和 Visual Basic 项目类型可以用作基础项目子类型;C + + 项目类型不能。 为项目子类型，你自己的项目类型还可以用作基础。 有关详细信息，请参阅[项目子类型](../../extensibility/internals/project-subtypes.md)。  
  
 [Web 项目](../../extensibility/internals/web-projects.md)  
 介绍 Web 项目中，创建 Web 应用程序。  
  
 [生成新项目： 揭秘，第 1 部分](../../extensibility/internals/new-project-generation-under-the-hood-part-one.md)和[生成新项目： 揭秘，第二部分](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)  
 介绍什么实际发生的情况时创建新的项目。  
  
 [VSSDK 示例](../../misc/vssdk-samples.md)  
 说明 VSSDK 处理项目和解决方案的示例。  
  
## <a name="related-sections"></a>相关章节  
 [Visual Studio SDK 内](../../extensibility/internals/inside-the-visual-studio-sdk.md)  
 介绍了 Visual Studio 可扩展性的不同方面。

