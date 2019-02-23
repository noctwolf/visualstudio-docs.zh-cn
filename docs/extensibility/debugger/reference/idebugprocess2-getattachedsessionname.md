---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa932817c796249803558ad1eb877f620198b3e4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703535"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
获取正在调试此进程的会话的名称。 IDE 可以调试特定计算机上的特定进程的用户显示此信息。

> [!NOTE]
>  此方法已弃用，并且它的实现应始终返回`E_NOTIMPL`。

## <a name="syntax"></a>语法

```
HRESULT GetAttachedSessionName(
   BSTR* pbstrSessionName
);
```

#### <a name="parameters"></a>参数
 `pbstrSessionName`

## <a name="return-value"></a>返回值
 此方法应始终返回`E_NOTIMPL`。

## <a name="see-also"></a>请参阅
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)