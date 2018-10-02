---
title: 网站支持 |Microsoft Docs
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
- web site projects
ms.assetid: ce9f4266-bb64-4c09-be88-4bd6413f60d0
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 128c5d94bbb508e6cf168f3de5662ba88b9d6193
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484165"
---
# <a name="web-site-support"></a>网站支持
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[网站上支持](https://docs.microsoft.com/visualstudio/extensibility/internals/web-site-support)。  
  
网站项目系统是创建 Web 项目的项目系统。 反过来，web 项目创建 Web 应用程序。 网站项目会生成一个可执行文件，每个网页关联的代码。 其他可执行文件是从 /App_Code 文件夹中的源代码文件生成的。  
  
 通过将模板和注册属性添加到现有的项目系统创建网站项目系统。 其中一个属性选择的语言的 IntelliSense 提供程序。 IntelliSense 提供程序实现处理引用，并请求未缓存智能 Web 页时调用的语言编译器。  
  
 必须已注册的语言编译器用于编译网页[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]。 可以使用[\<编译器 > 元素](http://msdn.microsoft.com/library/7a151659-b803-4c27-b5ce-1c4aa0d5a823)在 Web.config 文件以注册的编译器，如以下示例所示：  
  
```  
<system.codedom>  <compilers>    <compiler language="py;IronPython" extension=".py"       type="IronPython.CodeDom.PythonProvider, IronPython,       Version=1.0.2391.18146, Culture=neutral,       PublicKeyToken=b03f5f7f11d50a3a" />  </compilers></system.codedom>  
```  
  
## <a name="in-this-section"></a>本节内容  
 [网站支持模板](../../extensibility/internals/web-site-support-templates.md)  
 列出可用于创建新网站项目和关联的项的模板。  
  
 [网站支持属性](../../extensibility/internals/web-site-support-attributes.md)  
 显示连接到的网站项目的注册属性[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]和[!INCLUDE[vstecasp](../../includes/vstecasp-md.md)]。  
  
## <a name="related-sections"></a>相关章节  
 [Web 项目](../../extensibility/internals/web-projects.md)  
 概述了两种类型的 Web 项目、 网站项目和 Web 应用程序项目。

