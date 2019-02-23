---
title: IDebugDocumentText2::GetSize | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentText2::GetSize
helpviewer_keywords:
- IDebugDocumentText2::GetSize
ms.assetid: bf515a8f-dcee-4004-8f81-543d547ceaae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d5749a4bd738d6ec7edbf926542dbde0eb59db6
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685542"
---
# <a name="idebugdocumenttext2getsize"></a>IDebugDocumentText2::GetSize
检索在此位置上的文档中的文本的大小。

## <a name="syntax"></a>语法

```cpp
HRESULT GetSize( 
   ULONG* pcNumLines,
   ULONG* pcNumChars
);
```

```csharp
int GetSize( 
   ref uint pcNumLines,
   ref uint pcNumChars
);
```

#### <a name="parameters"></a>参数
 `pcNumLines`

 [out]返回文本的行数。

 `pcNumChars`

 [out]返回文本的字符数。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注

 [C + +]如果不需要特定的值，请将传递该参数为 NULL。


 [C#仅]必须指定这两个参数。

## <a name="see-also"></a>请参阅
- [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)