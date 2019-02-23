---
title: IDebugDocumentPositionOffset2::GetRange |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2::GetRange
ms.assetid: 27da7130-0932-4f97-abde-05e6fb018606
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e8b309af47aed94c45eca418b390be041f66f609
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686907"
---
# <a name="idebugdocumentpositionoffset2getrange"></a>IDebugDocumentPositionOffset2::GetRange
检索当前的文档位置的范围。

## <a name="syntax"></a>语法

```cpp
HRESULT GetRange(
   DWORD* pdwBegOffset,
   DWORD* pdwEndOffset
);
```

```csharp
public int GetRange(
   ref uint pdwBegOffset,
   ref uint pdwEndOffset
);
```

#### <a name="parameters"></a>参数
 `pdwBegOffset`

 [in、 out]为范围的起始位置的偏移量。 如果不需要此信息，请将此参数设置为 null 值。

 `pdwEndOffset`

 [in、 out]为范围的结束位置的偏移量。 如果不需要此信息，请将此参数设置为 null 值。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 在一个位置断点的文档位置中指定的范围是调试引擎 (DE) 用于实际影响代码的语句继续搜索。 例如，考虑以下代码：

```
Line 5: // comment
Line 6: x = 1;
```

 第 5 行分配到正在调试的程序的任何代码。 如果行 5 设置断点调试器想 DE 向前搜索一定影响代码的第一行，调试器会指定一系列，包括其他候选行断点可能会正确放。 DE 将然后向前搜索这些行直到找到可接受断点的行。

## <a name="see-also"></a>请参阅
- [IDebugDocumentPositionOffset2](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2.md)
- [GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)