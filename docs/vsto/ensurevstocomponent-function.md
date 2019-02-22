---
title: EnsureVSTOComponent 函数
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f99ccb4cb76f942852716abf1fcb0c0f280decbd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621430"
---
# <a name="ensurevstocomponent-function"></a>EnsureVSTOComponent 函数
  此 API 支持 Office 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```csharp
HRESULT EnsureVSTOComponent(
    IVSTProject *pProject
);
```

#### <a name="parameters"></a>参数

|参数|描述|
|---------------|-----------------|
|*pProject*|不要使用。|

## <a name="return-value"></a>返回值
 如果函数成功，它将返回 **，则为 S_OK**。 如果函数失败，则返回错误代码。
