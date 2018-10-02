---
title: 如何： 注册服务 |Microsoft Docs
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
ms.assetid: d086be78-ec3c-43cc-b799-5180a71e19f1
caps.latest.revision: 16
manager: douge
ms.openlocfilehash: a242a13893c7cd303adfe266c9609b7a71d251ba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477046"
---
# <a name="how-to-register-a-service"></a>如何：注册服务
托管包框架 (MPF) 提供一些特性来控制托管服务的注册。 RegPkg 实用工具使用这些属性注册与服务[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。  
  
## <a name="example"></a>示例  
 下面的代码摘自[VSSDK 示例](../misc/vssdk-samples.md)。  
  
 [!code-csharp[VSSDKRegisterService#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkregisterservice/cs/vssdkregisterservicepackage.cs#1)]
 [!code-vb[VSSDKRegisterService#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkregisterservice/vb/vssdkregisterservicepackage.vb#1)]  
  
 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>注册 SMyGlobalService 服务与[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 有关详细信息<xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute>并<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>，请参阅[注册和注销 Vspackage](../extensibility/registering-and-unregistering-vspackages.md)。  
  
 若要注册一个服务来替换具有相同名称的另一个服务，请使用<xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute>而不是<xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>。  
  
## <a name="robust-programming"></a>可靠编程  
 为了便于重新编译服务提供程序而不更改服务客户端（反之亦然），可以在单独的程序集模块中定义服务及其接口。 下面的代码来自 Reference.Services (C#) 示例中的 IMyGlobalService.cs 文件。  
  
 [!code-csharp[VSSDKRegisterService#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkregisterservice/cs/vssdkregisterservicepackage.cs#2)]
 [!code-vb[VSSDKRegisterService#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkregisterservice/vb/vssdkregisterservicepackage.vb#2)]  
  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>从非托管代码获取接口所需。  
  
> [!NOTE]
>  虽然可以对服务和接口使用相同的类型或 GUID，但建议将两者分开，因为一个服务可能会公开多个不同的接口。  
  
## <a name="see-also"></a>请参阅  
 [注册 Vspackage](http://msdn.microsoft.com/en-us/31e6050f-1457-4849-944a-a3c36b76f3dd)   
 [服务基础知识](../extensibility/internals/service-essentials.md)