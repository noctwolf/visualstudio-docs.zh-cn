---
title: VSTextBuffer 对象 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e763b8006dd2c01f8e2ee4beeffa7c78100b15b3
ms.sourcegitcommit: 56ae5032d99d948aae0548ae318ca2bae97ea962
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2018
ms.locfileid: "39586296"
---
# <a name="vstextbuffer-object"></a>VSTextBuffer 对象
文本缓冲区对象表示 Unicode 文本，这是通常与文件相关联的流。 一个<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>上下文之外的核心编辑器，如中所示，一个向导，可以使用对象。  
  
 下表显示了接口的`VSTextBuffer`。  
  
|方法|描述|  
|------------|-----------------|  
|[不需要此行为](http://msdn.microsoft.com/library/windows/desktop/ms683797)|标准 OLE 接口。 用于处理在缓冲区中撤消/重做。|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|标准 OLE 接口。|  
|[IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|标准 OLE 接口。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|可以创建复合音操作 （即，在撤消/重做单个单元进行分组的操作）。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|使文档数据管理的文本缓冲区的持久性。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|提供基本服务;由多个客户端。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|用于搜索缓冲区。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|提供了读取和写入功能使用二维坐标。 继承自 `IVsTextBuffer`。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|提供了读取和写入功能使用一维的坐标。 继承自 `IVsTextBuffer`。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|提供快速、 面向流的顺序访问缓冲区中的文本。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|提供对属性的泛型集合的访问。 最重要属性是缓冲区的名称或的名字对象。 通过创建 GUID 并使用它作为键，可以使用此接口在缓冲区中存储自己的随机数据。|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|支持连接点的事件。|  
  
## <a name="remarks"></a>备注  
 `VSTextBuffer`通常通过找到`QueryInterface`上调用`IVsTextBuffer`。 有关详细信息，请参阅[文本缓冲区](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [图编辑](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)