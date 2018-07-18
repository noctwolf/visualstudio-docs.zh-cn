---
title: 网站支持 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d3da310c6695598eef36998cc562f6d477eff29
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139846"
---
# <a name="web-site-support"></a>网站支持
网站项目系统是创建 Web 项目的项目系统。 反过来，web 项目创建 Web 应用程序。 网站项目会生成一个可执行文件，每个网页关联代码。 其他可执行文件是从源代码文件 /App_Code 文件夹中生成的。  
  
 通过将模板和注册属性添加到现有的项目系统创建网站项目系统。 其中一个属性选择的语言的 IntelliSense 提供程序。 IntelliSense 提供程序实现处理引用，并在不缓存智能网页的请求时调用的语言编译器。  
  
 必须已注册的语言编译器用于编译网页[!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]。 你可以使用[\<编译器 > 元素](/dotnet/framework/configure-apps/file-schema/compiler/compiler-element)一个要注册的编译器，如以下示例所示的 Web.config 文件中：  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>本节内容  
 [网站支持模板](../../extensibility/internals/web-site-support-templates.md)  
 列出可用于创建新网站项目和关联的项的模板。  
  
 [网站支持属性](../../extensibility/internals/web-site-support-attributes.md)  
 显示连接到网站项目的注册属性[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]和[!INCLUDE[vstecasp](../../code-quality/includes/vstecasp_md.md)]。  
  
## <a name="related-sections"></a>相关章节  
 [Web 项目](../../extensibility/internals/web-projects.md)  
 提供两种类型的 Web 项目、 网站项目和 Web 应用程序项目的概述。