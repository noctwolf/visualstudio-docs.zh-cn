---
title: IDebugModule3::IsUserCode |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugModule3::IsUserCode
helpviewer_keywords:
- IDebugModule3::IsUserCode
ms.assetid: 77022946-bb8b-4114-aa81-614df6e54b13
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8e44f70741e6f47bc628a7952979bead0bfba23d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112935"
---
# <a name="idebugmodule3isusercode"></a>IDebugModule3::IsUserCode
检索的模块是否在或不表示用户代码的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsUserCode(  
   BOOL* pfUser  
);  
```  
  
```csharp  
int IsUserCode(  
   out int pfUser  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pfUser`  
 [out]非零 (`TRUE`) 如果模块表示用户代码，零 (`FALSE`) 如果它不存在。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)