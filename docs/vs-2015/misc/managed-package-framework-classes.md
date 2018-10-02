---
title: 托管包框架类 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managed package framework, helper classes
- managed package helper classes
- Visual Studio SDK, managed package helper classes
- classes [Visual Studio SDK], managed package framework
ms.assetid: 15aedcc3-c79a-460b-b620-43223f1ae81e
caps.latest.revision: 24
manager: douge
ms.openlocfilehash: 38f159df52c99554ed931269f29ad57e72745b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482336"
---
# <a name="managed-package-framework-classes"></a>托管包框架类
使用托管代码，托管包框架 (MPF) 类可以用于创建 Vspackage。 它们提供许多 VSPackage 接口的默认实现。 通过隐藏实现细节和复杂性，MPF 使你能够创建[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]最少量的代码的集成产品。  
  
> [!WARNING]
>  大多包含托管包框架类的程序集都附带有 Visual Studio SDK。 可以在 [项目的托管包框架](http://mpfproj11.codeplex.com/)下载适用于项目 的托管包框架的源代码。  
  
## <a name="mpf-namespaces"></a>MPF 命名空间  
 下表列出了由提供的 MPF 命名空间[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]。  
  
|命名空间|内容|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio>|包含用于处理 COM 错误的有用类[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]常量和 Win32 windows。|  
|<xref:Microsoft.VisualStudio.Package>|包含托管的代码包装[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]项目、 编辑器和 MSBuild。|  
|<xref:Microsoft.VisualStudio.Shell>|包含可从其派生许多常见 Visual Studio 对象的实现的 MPF 基类。|  
|<xref:Microsoft.VisualStudio.Shell.Design>|包含[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]设计器扩展。|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization>|包含[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]序列化设计器扩展。|  
|<xref:Microsoft.VisualStudio.Shell.Design.Serialization.CodeDom>|包含[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]CodeDom 设计器扩展。|  
|<xref:Microsoft.VisualStudio.Shell.Flavor>|支持项目子类型（也称为“风格”）。|  
  
## <a name="see-also"></a>请参阅  
 [Vspackage 和托管的包框架](../misc/vspackages-and-the-managed-package-framework.md)   
 [使用 Visual Studio 互操作程序集](../extensibility/internals/using-visual-studio-interop-assemblies.md)   
 [VSPackage 和托管包框架](../misc/vspackages-and-the-managed-package-framework.md)