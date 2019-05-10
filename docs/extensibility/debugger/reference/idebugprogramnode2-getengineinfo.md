---
title: IDebugProgramNode2::GetEngineInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetEngineInfo
helpviewer_keywords:
- IDebugProgramNode2::GetEngineInfo
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c31d3a858af2886a27a51e22e131cb89b2234d6e
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "65459071"
---
# <a name="idebugprogramnode2getengineinfo"></a>IDebugProgramNode2::GetEngineInfo
获取名称和标识符的运行程序的调试引擎 (DE)。

## <a name="syntax"></a>语法

```cpp
HRESULT GetEngineInfo ( 
   BSTR* pbstrEngine,
   GUID* pguidEngine
);
```

```csharp
int GetEngineInfo(
   out string pbstrEngine,
   out Guid pguidEngine
);
```

## <a name="parameters"></a>参数
 `pbstrEngine`\

 [out]返回的运行程序 DE 名称 (C++-特定： 这可以是 null 指针，该值指示调用方不希望该引擎的名称)。

 `pguidEngine`\

 [out]返回运行程序 DE 的全局唯一标识符 (C++-特定： 这可以是 null 指针，该值指示调用方不感兴趣的引擎的 GUID)。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)