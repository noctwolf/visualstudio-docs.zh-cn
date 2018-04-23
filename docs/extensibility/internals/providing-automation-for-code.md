---
title: 提供代码的自动化 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9f9dbb7a8ddad39f01f5b29443168eebe12a2da8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="providing-automation-for-code"></a>提供代码的自动化
创建自动化模型为你的代码不是必需的。 环境 SDK 不提供有关执行此操作的示例。 代码模型见解，请参阅<xref:EnvDTE.CodeModel>对象。  
  
 若要实现代码模型，则必须实现由您的内部数据结构的所有接口。 对象必须源自`IDispatch`类。  
  
 扩展时，对象<xref:EnvDTE.CodeModel>和<xref:EnvDTE.FileCodeModel>，从可用<xref:EnvDTE.Project>对象，并如下所示：  
  
 <xref:EnvDTE.Project.CodeModel%2A>  
  
 <xref:EnvDTE.ProjectItem.FileCodeModel%2A>  
  
 你可以选择实现只需`CodeModel`或`FileCodeModel`从返回的对象中接口你`Project`和<xref:EnvDTE.ProjectItem>对象。 提供从适合于你的项目系统此接口的任何功能。  
  
 如果你想要添加的功能，例如方法或属性，未提供的标准`CodeModel`和`FileCodeModel`接口，创建你自己继承自标准的接口。 请务必记下此信息与你的项目系统以便最终用户将了解来查找它。 返回的标准接口，但用户可以调用`QueryInterface`方法或强制转换为你的接口，如果它已知的存在。  
  
## <a name="see-also"></a>另请参阅  
 [自动化模型概述](../../extensibility/internals/automation-model-overview.md)