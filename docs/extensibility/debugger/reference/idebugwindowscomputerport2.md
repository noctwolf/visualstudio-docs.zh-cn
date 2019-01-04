---
title: IDebugWindowsComputerPort2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugWindowsComputerPort2 interface
ms.assetid: 25f327b8-0303-4268-88d1-74df630436aa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1e2a037ad0477be258e33879d1dc336fa67cc915
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53965283"
---
# <a name="idebugwindowscomputerport2"></a>IDebugWindowsComputerPort2
允许的目标计算机的信息进行查询。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugWindowsComputerPort2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 此接口是由会话调试管理器的 port 对象实现的。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugWindowsComputerPort2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)|检索有关计算机上的信息的调试器中运行。|  
  
## <a name="requirements"></a>要求  
 标头：Msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll