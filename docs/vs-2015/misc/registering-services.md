---
title: 注册服务 |Microsoft Docs
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
- services, registering
ms.assetid: c4ebac40-0374-4dda-948e-06fdda0e9c81
caps.latest.revision: 8
manager: douge
ms.openlocfilehash: f56c73bbb09c659a76083e511d79d487402477ac
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479386"
---
# <a name="registering-services"></a>注册服务
若要支持按需加载，服务提供商必须注册其全球服务和[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。  
  
 在开发期间，托管的服务提供商注册服务和服务重写方法是将特性添加到包的源代码中然后生成包[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]IDE。 这会在生成的程序集上运行 RegPkg.exe 实用程序，注册包并为部署做准备。 有关详细信息，请参阅[如何： 注册服务](../misc/how-to-register-a-service.md)。  
  
 非托管的服务提供商必须注册它们提供的服务[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]在服务中部分或服务重写的系统注册表的部分。 下面的.reg 文件片断演示注册服务 SVsTextManager 的方式：  
  
```  
[HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\<version number>\Services\{F5E7E71D-1401-11d1-883B-0000F87579D2}]  
@="{F5E7E720-1401-11d1-883B-0000F87579D2}"  
"Name"="SVsTextManager"  
```  
  
 在上面的示例中，版本号是版本[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，如 7.1 或 8.0，{F5E7E71D-1401-11d1-883B-0000F87579D2} 的密钥是服务、 SVsTextManager 和默认值 {的服务标识符 (SID)F5E7E720-1401-11d1-883B-0000F87579D2} 是包的文本管理器提供服务的 VSPackage 的 GUID。  
  
## <a name="remote-services-and-background-threads"></a>远程服务和后台线程  
 你提供的服务不会自动在远程方式下可用，或供后台线程使用。 若要使其可用，必须生成并注册类型库。  
  
 通过使用 Visual Studio 库 (VSL) 的非托管代码，可以通过这种方式注册类型库：  
  
```  
#define VSL_REGISTER_TYPE_LIB TRUE  
#include <VSLPackageDllEntryPoints.cpp>  
```  
  
 通过托管代码，可以添加如下生成后步骤：  
  
```  
regasm /tlb MyAssembly.dll  
```  
  
## <a name="see-also"></a>请参阅  
 [使用并提供服务](../extensibility/using-and-providing-services.md)   
 [服务基础知识](../extensibility/internals/service-essentials.md)