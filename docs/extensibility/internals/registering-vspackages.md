---
title: "注册 Vspackage |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 119e6dc088c6f6e80d79ab096d97b7404c530611
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="registering-vspackages"></a>注册 Vspackage
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]依赖于.pkgdef 文件来介绍并找到 VSPackage。 一个.pkgdef 文件包含否则将添加到系统注册表中的所有注册信息。 通过将特性添加到源代码，然后运行注册托管的 Vspackage [CreatePkgDef 实用工具](../../extensibility/internals/createpkgdef-utility.md)上生成的程序集生成.pkgdef 文件。  
  
## <a name="in-this-section"></a>本节内容  
 [指定 VS Shell 的 VSPackage 文件位置](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)  
 介绍 Vspackage 的加载路径。  
  
 [注册和注销 Vspackage](../../extensibility/registering-and-unregistering-vspackages.md)  
 说明如何注册 VSPackage。  
