---
title: 提供适用于代码自动化 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4adbc5385923e071e158734500e30a6a05832a1f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54976214"
---
# <a name="providing-automation-for-code"></a>提供适用于 Code 的自动化
不需要创建你的代码的自动化模型。 环境 SDK 不提供用于执行此操作的一个示例。 代码模型见解，请参阅<xref:EnvDTE.CodeModel>对象。  
  
 若要实现代码模型，必须实现任何接口，这由您的内部数据结构。 对象必须派生自`IDispatch`类。  
  
 扩展时，对象<xref:EnvDTE.CodeModel>并<xref:EnvDTE.FileCodeModel>，可从<xref:EnvDTE.Project>对象，并如下所示：  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 你可以选择实现只需`CodeModel`或`FileCodeModel`接口从返回的对象中你`Project`和<xref:EnvDTE.ProjectItem>对象。 提供此接口的适用于你的项目系统中的任何功能。  
  
 如果你想要添加功能，例如方法或属性，就无法从标准`CodeModel`和`FileCodeModel`接口，创建您自己继承自标准的界面。 请确保与你的项目系统进行记录，以便最终用户将知道要查找它。 返回的标准接口，但用户可以调用`QueryInterface`方法或强制转换为你的接口，如果它已知的存在。  
  
## <a name="see-also"></a>请参阅  
 [自动化模型概述](../../extensibility/internals/automation-model-overview.md)