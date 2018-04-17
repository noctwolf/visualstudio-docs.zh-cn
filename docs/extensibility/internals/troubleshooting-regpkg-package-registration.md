---
title: 故障排除 RegPkg 程序包注册 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4857e41888962a92dced87d63fa2b63161ecac55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="troubleshooting-regpkg-package-registration"></a>故障排除 RegPkg 程序包注册
> [!NOTE]
>  在 Visual Studio 中注册包的首选的方法是使用.pkgdef 文件。 这使得扩展部署而无需访问系统注册表。 通过使用创建 Pkgdef 文件[CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md)。  
  
 若要通过使用中的 RegPkg 注册包[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]，必须使用适合于你的包的 RegPkg 的版本。  
  
## <a name="regpkg-versions-related-to-package-versions"></a>与包版本相关的 RegPkg 版本  
 有两个版本的 RegPkg。 一个版本包括在[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 使用此版本注册包已生成通过使用以下程序集之一：  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 它无法注册通过使用早期 Microsoft.VisualStudio.Shell.dll 程序集生成的包。  
  
 RegPkg 的早期版本可以注册通过使用 Microsoft.VisualStudio.Shell.dll 程序集生成的包。 但是，它无法注册使用该程序集的更高版本生成的包。  
  
## <a name="see-also"></a>另请参阅  
 [VSPackage](../../extensibility/internals/vspackages.md)