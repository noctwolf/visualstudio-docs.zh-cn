---
title: BP_LOCATION_DATA_STRING | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 44fbd40528196fdebee852d89108cf6205e5db71
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318183"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
用于设置数据断点的基于用户可以从集成的开发环境 (IDE) 中输入的字符串。

## <a name="syntax"></a>语法

```cpp
typedef struct _BP_LOCATION_DATA_STRING {
    IDebugThread2* pThread;
    BSTR           bstrContext;
    BSTR           bstrDataExpr;
    DWORD          dwNumElements;
} BP_LOCATION_DATA_STRING;
```

## <a name="members"></a>成员
`pThread`  
[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)对象，表示该断点发生时所在的线程。

`bstrContext`  
在代码内的断点，通常显示调用堆栈上的方法或函数名称的上下文。

`bstrDataExpr`  
用户输入的数据字符串以设置断点。

`dwNumElements`  
断点发生的数据字符串中的元素数。

## <a name="remarks"></a>备注
此结构是的成员[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)结构作为联合的一部分。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
[结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
