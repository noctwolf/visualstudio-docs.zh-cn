---
title: 如何：使用文本标记 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - using text markers
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bca32c007e29e910f167df66c92d04bec637f9b3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60105445"
---
# <a name="how-to-use-text-markers"></a>如何：使用文本标记
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

文本标记可用于编辑<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>对象。  
  
## <a name="procedures"></a>过程  
  
#### <a name="to-apply-text-markers"></a>若要将文本标记应用  
  
1. 获取的实例<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager>类。  
  
    > [!NOTE]
    >  核心编辑器会自动将标准文本标记应用于任何文档的编辑，并且不应需要显式应用标准文本标记。  
  
2. 获取通过调用感兴趣的标记的标记类型 ID<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A>方法替换`GUID`你想要使用的文本标记。  
  
    > [!NOTE]
    >  不要使用`GUID`VSPackage 或提供文本标记的服务。  
  
3. 使用标记类型 ID 获取通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A>作为参数来调用方法<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A>方法或<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A>方法将文本标记应用于给定文本的区域。  
  
#### <a name="to-add-features-to-text-markers"></a>若要将功能添加到文本标记  
  
1. 可能需要将其他功能添加到文本标记，如工具提示、 特殊的上下文菜单中或处理程序的特殊情况。 为此，请执行以下操作：  
  
2. 创建一个对象，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>接口。  
  
3. 如果需要其他功能，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>，并<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced>上实现的相同对象的接口<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>接口。  
  
4. 传递<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient>创建，到对调用的接口<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A>方法或<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A>方法用于将文本标记应用到给定区域的文本。  
  
5. 添加到文本标记区域的上下文菜单支持时，必须创建菜单。  
  
     有关如何创建上下文菜单，请参阅详细信息[上下文菜单](../extensibility/context-menus.md)。  
  
6. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]环境调用的方法提供的接口，如<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A>方法，或<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A>方法根据需要。  
  
## <a name="see-also"></a>请参阅  
 [旧版 API 中使用文本标记](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [如何：添加标准文本标记](../extensibility/how-to-add-standard-text-markers.md)   
 [如何：创建自定义文本标记](../extensibility/how-to-create-custom-text-markers.md)   
 [如何：实现错误标记](../extensibility/how-to-implement-error-markers.md)
