---
title: 提供的服务 (源代码管理 VSPackage) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f94efff27ea45dc070e34f26d85be4bd7ff5b50
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54936900"
---
# <a name="services-provided-source-control-vspackage"></a>提供的服务（源代码管理 VSPackage）
服务是通过该功能被共享之间的 Visual Studio 集成的开发环境 (IDE) 和其已安装的 Vspackage 以及 Vspackage 之间的主要机制。 服务和 Visual Studio IDE 中的其重要性的详细说明，请参阅[使用和提供服务](../../extensibility/using-and-providing-services.md)。  
  
## <a name="the-source-control-service"></a>源代码管理服务  
 Visual Studio 提供了两个层的服务、 IDE 级别服务和包级别服务。 Visual Studio IDE 以本机方式提供 IDE 级别服务。 源代码管理包使用其中一些服务。 源代码管理包作为 VSPackage 通过提供其自己的专用源代码管理服务共享其源代码管理功能。 源代码管理包封装实现的协定可以由 Visual Studio IDE 的窗体中的源控件相关接口集。  
  
## <a name="see-also"></a>请参阅  
 [设计元素](../../extensibility/internals/source-control-vspackage-design-elements.md)