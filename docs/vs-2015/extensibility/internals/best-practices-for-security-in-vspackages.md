---
title: Vspackage 中安全性的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security [Visual Studio SDK]
- security best practices, VSPackages
- best practices, security
ms.assetid: 212a0504-cf6c-4e50-96b0-f2c1c575c0ff
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 80c27618582f42f1647e49cbf3f64d6b493dfd8d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49203588"
---
# <a name="best-practices-for-security-in-vspackages"></a>VSPackage 中安全性的最佳做法
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

若要安装[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]计算机时，你必须在运行具有管理凭据的上下文。 安全和部署的基本单位[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]应用程序是[Vspackage](../../extensibility/internals/vspackages.md)。 必须使用注册 VSPackage [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，这也要求管理凭据。  
  
 管理员拥有完全权限写入注册表和文件系统中，并运行任何代码。 必须具有这些权限以开发、 部署或安装 VSPackage。  
  
 一旦安装，VSPackage 是完全受信任。 由于此高级别的权限与 VSPackage 相关联，很可能会无意中安装具有恶意企图的 VSPackage。  
  
 用户应确保它们仅从受信任来源安装 Vspackage。 公司开发 VSPackages 应强命名，并加上签名，以确保用户该篡改阻止。 公司开发 VSPackages 应检查其外部依赖项，如 web 服务和远程安装，以评估并更正任何安全问题。  
  
 详细信息，请参阅.NET Framework 安全编码准则 ([http://msdn.microsoft.com/library/d55zzx87.aspx](http://msdn.microsoft.com/library/d55zzx87.aspx))。  
  
## <a name="see-also"></a>请参阅  
 [外接程序安全性](http://msdn.microsoft.com/library/44a5c651-6246-4310-b371-65378917c799)   
 [DDEX 安全](http://msdn.microsoft.com/en-us/44a52a70-5c98-450e-993d-4a3b32f69ba8)

