---
title: RegPkg 包注册进行故障排除 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8a5d8a8a63aabafb9c658d43fc90c1bb28918c8e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54943534"
---
# <a name="troubleshooting-regpkg-package-registration"></a>RegPkg 包注册疑难解答
> [!NOTE]
>  在 Visual Studio 中注册包的首选的方法是通过使用.pkgdef 文件。 这样可以扩展部署而无需访问系统注册表。 通过使用创建 Pkgdef 文件[CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md)。  
  
 若要使用 RegPkg 中的注册包[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，必须使用适合于您的包的 RegPkg 的版本。  
  
## <a name="regpkg-versions-related-to-package-versions"></a>与包版本相关的 RegPkg 版本  
 有两个版本的 RegPkg。 一个版本包含在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 使用此版本已通过以下程序集生成的包注册：  
  
1. Microsoft.VisualStudioShell.9.0.dll  
  
2. Microsoft.VisualStudioShell.10.0.dll  
  
3. Microsoft.VisualStudioShell.11.0.dll  
  
   它不能注册已使用早期 Microsoft.VisualStudio.Shell.dll 程序集生成的包。  
  
   在早期版本的 RegPkg 可以注册使用 Microsoft.VisualStudio.Shell.dll 程序集生成的包。 但是，它不能使用该程序集的更高版本生成的包进行注册。  
  
## <a name="see-also"></a>请参阅  
 [VSPackage](../../extensibility/internals/vspackages.md)