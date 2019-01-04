---
title: 注册 Vspackage |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d4b5bedbfdeaab6fa3d7d8efe4479a8b7f3e4de4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842601"
---
# <a name="registering-vspackages"></a>注册 VSPackage
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 依赖于要描述和定位 VSPackage 的.pkgdef 文件。 .Pkgdef 文件包含否则会添加到系统注册表的所有注册信息。 通过将属性添加到源代码，然后运行注册托管的 Vspackage [CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md)上生成的程序集生成.pkgdef 文件。  
  
## <a name="in-this-section"></a>本节内容  
 [指定 VS Shell 的 VSPackage 文件位置](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 介绍 Vspackage 的加载路径。  
  
 [注册和注销 Vspackage](../../extensibility/registering-and-unregistering-vspackages.md)  
 介绍如何注册 VSPackage。  
