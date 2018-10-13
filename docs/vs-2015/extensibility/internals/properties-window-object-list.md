---
title: 属性窗口对象列表 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6fd821da5d54afdb7ea8b3d16dc32f818222a961
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49183100"
---
# <a name="properties-window-object-list"></a>属性窗口对象列表
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

中的对象列表**属性**窗口是下拉列表，您可以将所选内容更改为一个或多个所选的 windows 中可用的其他对象。 选择此列表中的不同对象从触发调用<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A>通知环境已选择一个新的对象。 中显示的信息**属性**窗口然后更改为显示与新选择的对象相关联的属性。  
  
## <a name="the-object-list"></a>对象列表  
 对象列表包含两个字段: （以粗体显示） 的对象名称和对象类型。  
  
 以粗体显示的对象类型的左边显示对象名称进行检索的对象本身使用`Name`属性提供的<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>接口。 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>则只能在<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>，返回<xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo>为该接口的组件类。 **属性**窗口使用<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>获取组件类，显示为下拉列表中的对象名称的名称。  
  
 如果对象不具有`Name`属性，名称未显示在对象列表的名称区域中。 如果想要显示对象列表中的名称，您可以将 Name 属性添加到对象。  
  
 如果 COM 对象不实现<xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>，则**属性**窗口左侧和右侧的列表显示接口名称而不是对象名称。  
  
## <a name="see-also"></a>请参阅  
 [扩展属性](../../extensibility/internals/extending-properties.md)

