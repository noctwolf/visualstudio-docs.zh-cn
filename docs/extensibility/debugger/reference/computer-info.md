---
title: COMPUTER_INFO |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- COMPUTER_INFO structure
ms.assetid: 943085b2-f165-462d-9a4e-2086f0cdfff4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 183c079206dd4c16a9301e370abec2f9351b1f61
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56316829"
---
# <a name="computerinfo"></a>COMPUTER_INFO
描述在其运行调试器的计算机。

## <a name="syntax"></a>语法

```cpp
typedef struct tagCOMPUTER_INFO
{
    WORD wProcessorArchitecture;
    WORD wSuiteMask;
    DWORD dwOperatingSystemVersion;
} COMPUTER_INFO;
```

```csharp
public struct COMPUTER_INFO
{
    public ushort wProcessorArchitecture;
    public ushort wSuiteMask;
    public uint dwOperatingSystemVersion;
}
```

## <a name="terms"></a>术语
wProcessorArchitecture  
标识微处理器体系的结构。

wSuiteMask  
标识套件掩码。

dwOperatingSystemVersion  
操作系统版本号。

## <a name="remarks"></a>备注
返回此结构[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)方法。

## <a name="requirements"></a>要求
标头：Msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
[结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)  
[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)
