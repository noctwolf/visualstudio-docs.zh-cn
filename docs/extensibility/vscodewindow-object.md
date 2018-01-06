---
title: "VSCodeWindow 对象 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2de0998a3d89c1af3e18fa60aa3f8511716f6165
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="vscodewindow-object"></a>VSCodeWindow 对象
代码窗口是可以包含一个或多个文本视图，通常一个专用的文档窗口<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>对象。  
  
 体系结构上，代码窗口是在窗口框架内的文档窗口。 就功能而言，代码窗口是只需一个具有附加功能的文档窗口。 在多文档界面 (MDI) 模式下，代码窗口是 MDI 子框架。 有关详细信息，请参阅[自定义代码窗口中，使用旧 API](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)。  
  
 下表包含中的接口<xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>对象。  
  
|方法|描述|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|提供通用访问机制来查找全局唯一标识符 (GUID) 标识的服务。|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|表示包含一个或多个代码视图的多个文档界面 (MDI) 子。|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|填充窗口框架。|  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [数字编辑](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)