---
title: BP_LOCATION_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1695c61a829cf1439ed773e48088430f36f8c653
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715656"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
指定断点请求断点的位置类型。

## <a name="syntax"></a>语法

```cpp
enum enum_BP_LOCATION_TYPE {
    BPLT_NONE               = 0x00000000,
    BPLT_FILE_LINE          = 0x00010000,
    BPLT_FUNC_OFFSET        = 0x00020000,
    BPLT_CONTEXT            = 0x00030000,
    BPLT_STRING             = 0x00040000,
    BPLT_ADDRESS            = 0x00050000,
    BPLT_RESOLUTION         = 0x00060000,
    BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,
    BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,
    BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,
    BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,
    BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,
    BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,
    BPLT_TYPE_MASK          = 0x0000FFFF,
    BPLT_LOCATION_TYPE_MASK = 0xFFFF0000
};
typedef DWORD BP_LOCATION_TYPE;
```

```csharp
public enum enum_BP_LOCATION_TYPE {
    BPLT_NONE               = 0x00000000,
    BPLT_FILE_LINE          = 0x00010000,
    BPLT_FUNC_OFFSET        = 0x00020000,
    BPLT_CONTEXT            = 0x00030000,
    BPLT_STRING             = 0x00040000,
    BPLT_ADDRESS            = 0x00050000,
    BPLT_RESOLUTION         = 0x00060000,
    BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,
    BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,
    BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,
    BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,
    BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,
    BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,
    BPLT_TYPE_MASK          = 0x0000FFFF,
    BPLT_LOCATION_TYPE_MASK = 0xFFFF0000
};
```

## <a name="members"></a>成员
BPLT_NONE 指定任何断点位置。

BPLT_FILE_LINE 指定为文件行断点的位置类型。

BPLT_FUNC_OFFSET 函数偏移量指定断点的位置类型。

BPLT_CONTEXT 作为上下文指定断点的位置类型。

BPLT_STRING 以字符串形式指定断点的位置类型。

BPLT_ADDRESS 指定为一个地址断点的位置类型。

BPLT_RESOLUTION 指定断点的位置类型来解决此问题。

BPLT_CODE_FILE_LINE 作为源代码的行中指定断点位置的类型。

BPLT_CODE_FUNC_OFFSET 代码函数偏移量为指定断点位置的类型。

BPLT_CODE_CONTEXT 作为代码上下文指定断点的位置类型。

BPLT_CODE_STRING 代码字符串形式指定断点的位置类型。

BPLT_CODE_ADDRESS 作为代码地址指定断点的位置类型。

BPLT_DATA_STRING 数据字符串形式指定断点的位置类型。

BPLT_TYPE_MASK 指定的位掩码，以便可以从值中提取断点类型。

BPLT_LOCATION_TYPE_MASK 指定的位掩码，以便可以从值中提取断点位置类型。

## <a name="remarks"></a>备注
作为参数传递给[GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)方法。

断点位置类型组成的断点类型和位置类型。 这意味着断点位置类型永远不会是只需断点类型 (例如， `BPT_CODE`) 或位置类型 (例如， `BPLT_FILE_LINE`)。 此枚举中包含有关当前支持的所有断点位置类型预定义的常量 (`BPLT_CODE_FILE_LINE`通过`BPLT_DATA_STRING`)。

`BPT_CODE` 并`BPT_DATA`属于[BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)枚举。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)
- [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)
