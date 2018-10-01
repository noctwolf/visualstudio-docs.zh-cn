---
title: 提供的服务 (源代码管理 VSPackage) |Microsoft Docs
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
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: aff288f68f32d3850cfa92d5999febd1c65572e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479814"
---
# <a name="services-provided-source-control-vspackage"></a>提供的服务（源代码管理 VSPackage）
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[服务提供 (源代码管理 VSPackage)](https://docs.microsoft.com/visualstudio/extensibility/internals/services-provided-source-control-vspackage)。  
  
服务是通过该功能被共享之间的 Visual Studio 集成的开发环境 (IDE) 和其已安装的 Vspackage 以及 Vspackage 之间的主要机制。 服务和 Visual Studio IDE 中的其重要性的详细说明，请参阅[使用和提供服务](../../extensibility/using-and-providing-services.md)。  
  
## <a name="the-source-control-service"></a>源代码管理服务  
 Visual Studio 提供了两个层的服务、 IDE 级别服务和包级别服务。 Visual Studio IDE 以本机方式提供 IDE 级别服务。 源代码管理包使用其中一些服务。 源代码管理包作为 VSPackage 通过提供其自己的专用源代码管理服务共享其源代码管理功能。 源代码管理包封装实现的协定可以由 Visual Studio IDE 的窗体中的源控件相关接口集。  
  
## <a name="see-also"></a>请参阅  
 [设计元素](../../extensibility/internals/source-control-vspackage-design-elements.md)

