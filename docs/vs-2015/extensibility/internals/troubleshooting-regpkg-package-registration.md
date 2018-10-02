---
title: RegPkg 包注册进行故障排除 |Microsoft Docs
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
- RegPkg
ms.assetid: f33f822f-697a-4bad-9c10-554b4c8f6246
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c5b2ebc470d12586957d77bbe7b076c053567742
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471234"
---
# <a name="troubleshooting-regpkg-package-registration"></a>RegPkg 包注册疑难解答
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[故障排除 RegPkg 包注册](https://docs.microsoft.com/visualstudio/extensibility/internals/troubleshooting-regpkg-package-registration)。  
  
> [!NOTE]
>  在 Visual Studio 中注册包的首选的方法是通过使用.pkgdef 文件。 这样可以扩展部署而无需访问系统注册表。 通过使用创建 Pkgdef 文件[CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md)。  
  
 若要使用 RegPkg 中的注册包[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，必须使用适合于您的包的 RegPkg 的版本。  
  
## <a name="regpkg-versions-related-to-package-versions"></a>与包版本相关的 RegPkg 版本  
 有两个版本的 RegPkg。 一个版本包含在[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。 使用此版本已通过以下程序集生成的包注册：  
  
1.  Microsoft.VisualStudioShell.9.0.dll  
  
2.  Microsoft.VisualStudioShell.10.0.dll  
  
3.  Microsoft.VisualStudioShell.11.0.dll  
  
 它不能注册已使用早期 Microsoft.VisualStudio.Shell.dll 程序集生成的包。  
  
 在早期版本的 RegPkg 可以注册使用 Microsoft.VisualStudio.Shell.dll 程序集生成的包。 但是，它不能使用该程序集的更高版本生成的包进行注册。  
  
## <a name="see-also"></a>请参阅  
 [发布产品](../../misc/releasing-a-visual-studio-integration-product.md)

