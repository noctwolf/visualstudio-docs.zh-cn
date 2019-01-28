---
title: 部署项目类型 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b42e4f879352a6edaf9171296b282accd9b1ae3f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55009903"
---
# <a name="deploy-project-types"></a>部署项目类型
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 安装新的项目类型聚合器 (*ProjectAggregator2.dll*) 以及还重新分发的 Windows Installer 程序包 (*ProjectAggregator2.msi*)。 托管代码项目类型必须使用新的聚合器。 ProjectAggregator2 突破了中的限制[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]项目聚合器，以防止托管代码项目类型正常工作。 以下步骤介绍如何更改你的 VSPackage 使用新的聚合器。  
  
1.  从解决方案中删除 NativeHierarchyWrapper 项目。  
  
2.  从您的安装程序中删除任何 NativeHierarchyWrapper 二进制文件。  
  
3.  添加*ProjectAggregator2.msi*你的设置。