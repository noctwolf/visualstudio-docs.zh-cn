---
title: 命令中互操作程序集的协定 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9daadac56fd74fe78cc5606f94927d1057496dd1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949930"
---
# <a name="command-contracts-in-interop-assemblies"></a>互操作程序集中的命令协定
处理命令的基本协定<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>接口是环境调用<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法以确定是否支持该命令，如果它受支持，以确定其状态和文本。 然后，环境调用<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>方法以执行该命令。  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法会处理相同的所有命令。 进一步的通信，如果 （例如，使用下拉列表中），需要由调用<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>使用适当的参数的方法。 这些参数的解释取决于指定的命令。  
  
 如果命令目标的输出参数中返回值，调用方负责始终释放所有已分配的资源。 由于此参数是一个变体，则清除该变体将释放的资源。  
  
 在命令必须在其中在层次结构窗口操作的情况下<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>必须使用接口。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>接口具有与类似的方法类似的协定：<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A>和<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>。  
  
## <a name="see-also"></a>请参阅  
 [Vspackage 如何添加用户界面元素](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Vspackage 中的命令传送](../../extensibility/internals/command-routing-in-vspackages.md)   
 [命令实现](../../extensibility/internals/command-implementation.md)