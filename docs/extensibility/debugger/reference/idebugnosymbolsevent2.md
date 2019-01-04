---
title: IDebugNoSymbolsEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugNoSymbolsEvent2 interface
ms.assetid: f6fb6388-47f6-4385-9ad5-95d62f9a7592
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 179d8a95bc54db90a98311626b34c3e17b68f7f0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53873114"
---
# <a name="idebugnosymbolsevent2"></a>IDebugNoSymbolsEvent2
信号[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试器用户界面以警告符号不找不到启动可执行文件的用户。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugNoSymbolsEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 由的调试引擎实现并由[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试器用户界面。  
  
## <a name="requirements"></a>要求  
 标头：Msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll