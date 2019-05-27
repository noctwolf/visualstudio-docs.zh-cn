---
title: IDebugDocumentContext2::GetDocument |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentContext2::GetDocument
helpviewer_keywords:
- IDebugDocumentContext2::GetDocument
ms.assetid: c6d46c5d-ade8-4dc8-9862-8fc7876658c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 43502bd66a136cc09a7deabe38ddee51a48ccbc9
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66204692"
---
# <a name="idebugdocumentcontext2getdocument"></a>IDebugDocumentContext2::GetDocument
获取包含此文档上下文中的文档。

## <a name="syntax"></a>语法

```cpp
HRESULT GetDocument( 
   IDebugDocument2** ppDocument
);
```

```csharp
int GetDocument( 
   out IDebugDocument2 ppDocument
);
```

## <a name="parameters"></a>参数
`ppDocument`\
[out]返回[IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)对象，表示包含此文档上下文中的文档。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法适用于这些提供直接向 IDE 的文档的调试引擎。 否则，此方法应返回`E_NOTIMPL`。

## <a name="see-also"></a>请参阅
- [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
- [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)