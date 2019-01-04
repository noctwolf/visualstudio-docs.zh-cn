---
title: 项目类型体系结构 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], architecture
ms.assetid: 9c1d940f-8a54-41f7-a8aa-c870e324371c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fea8273c1db662d5184d1afb71b5cd39789d6794
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53929301"
---
# <a name="project-types-architecture"></a>项目类型体系结构
本部分包含有关体系结构中的项目类型的详细的信息[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
 [项目模型的元素](../../extensibility/internals/elements-of-a-project-model.md)  
 列出了可以使用一种项目类型的服务和它必须实现的接口。  
  
 [项目模型核心组件](../../extensibility/internals/project-model-core-components.md)  
 描述项目类型都必须实现和 （可选） 可实现以提供其他功能的接口。  
  
 [何时创建项目类型](../../extensibility/internals/when-to-create-project-types.md)  
 可帮助您决定时必须创建一个项目类型以及何时使用另一个[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]如 Vspackage 和编辑器来实现相同目标的可扩展性功能。  
  
 [层次结构和选择](../../extensibility/internals/hierarchies-and-selection.md)  
 描述如何[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]使用层次结构和选定内容上下文提供一致和简化的用户体验。  
  
## <a name="related-sections"></a>相关章节  
 [项目子类型](../../extensibility/internals/project-subtypes.md)  
 介绍了如何项目子类型，可以自定义的项目系统的行为[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]和[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]。  
  
 [项目类型](../../extensibility/internals/project-types.md)  
 基本构建块的形式提供的项目概述[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]集成的开发环境 (IDE)。 提供了指向介绍项目生成和编译代码的控制的其他主题的链接。