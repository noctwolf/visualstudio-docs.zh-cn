---
title: 关闭源控件插件的兼容性警告 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, turning off compatibility warnings
- compatibility warnings, turning off
ms.assetid: ba318e12-921b-4b7a-a8c2-12c712be1dbf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2d3cffbd6a8b6c21aa6e958495b88eb51a5724a5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129545"
---
# <a name="how-to-turn-off-compatibility-warnings-for-source-control-plug-ins"></a>如何： 关闭源控件插件的兼容性警告
用户可能会看到几个兼容性警告时如何使用源代码管理中的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 显示警告取决于的源代码管理插件的功能，可以禁用详细信息。  
  
### <a name="to-disable-the-warning-to-ensure-optimal-source-control-integration-with-visual-studio"></a>若要禁用该警告:"以确保最佳的源代码管理集成，使用 Visual Studio..."  
  
-   设置以下注册表项 （如有必要，将添加值）：  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\DontDisplayCheckDotNETCompatible = dword: 00000001  
  
     此警告将显示所有非[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)]插件。  
  
### <a name="to-disable-the-warning-the-installed-source-control-provider-does-not-support-all-the-capabilities"></a>若要禁用该警告:"已安装的源代码管理提供程序不支持所有功能..."  
  
-   设置以下两个注册表值 （如有必要，请添加值）：  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\WarnedOldMSSCCIProvider = 00000000 时表示  
  
     HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl\UseOldSCC = dword: 00000001  
  
     如果源代码管理插件不显式支持可重入性为多个项目 （即，如果它可以一次检查中只有一个文件名和项目），将显示此警告。  
  
     最好是支持可重入性 (`SCC_CAP_REENTRANT`功能); 这样做将删除此警告。 但是，如果这种支持不是可能的则可以设置这些注册表项。  
  
## <a name="see-also"></a>另请参阅  
 [功能标志](../extensibility/capability-flags.md)