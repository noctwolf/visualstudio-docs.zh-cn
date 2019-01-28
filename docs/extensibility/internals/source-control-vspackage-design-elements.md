---
title: 源代码管理 VSPackage 设计元素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control packages, design elements
ms.assetid: edd3f2ff-ca32-4465-8ace-4330493b67bb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ab547ea2750658d40e20ab9101976dd93b236da
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55069478"
---
# <a name="source-control-vspackage-design-elements"></a>源代码管理 VSPackage 设计元素
在本部分中的主题概述了结构源代码管理 VSPackage 必须实现的深度集成。 它还列出了这些接口和源代码管理 VSPackage 的服务可以实现，和源代码管理 VSPackage 的接口和服务可以使用从其他[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]组件来支持其源控制模型和功能。  
  
## <a name="in-this-section"></a>本节内容  
 [VSPackage 结构](../../extensibility/internals/vspackage-structure-source-control-vspackage.md)  
 定义源代码管理 VSPackage 的结构。  
  
 [相关服务和接口](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)  
 列出了源控制与包相关接口和服务。  
  
 [提供的服务](../../extensibility/internals/services-provided-source-control-vspackage.md)  
 描述由源代码管理 VSPackage 提供的源控制服务。  
  
## <a name="related-sections"></a>相关章节  
 [创建源代码管理 VSPackage](../../extensibility/internals/creating-a-source-control-vspackage.md)  
 讨论如何创建源代码管理 VSPackage 不仅提供源代码管理功能，但可用于自定义[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]源代码管理 UI。