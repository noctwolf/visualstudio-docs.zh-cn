---
title: IApplicationDebuggerUI 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IApplicationDebuggerUI interface
ms.assetid: b8828817-ca24-4012-802c-7dcaeea65dc8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3c5f9e4cabeb4fba31bb039a7cf673ca1759860
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348901"
---
# <a name="iapplicationdebuggerui-interface"></a>IApplicationDebuggerUI 接口
由调试器集成的开发环境 (IDE) 实现 (除了`IApplicationDebugger`) 提供更好地控制调试器的用户界面 (UI) 的外部组件。  
  
 除了继承的方法之外`IUnknown`，则`IApplicationDebuggerUI`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|用户界面将包含到在调试器中的顶部指定的调试文档的窗口。|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|引入了包含给定的文档上下文页首调试器用户界面中的窗口和窗口滚动到上下文。|