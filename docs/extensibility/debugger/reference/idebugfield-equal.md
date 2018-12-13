---
title: IDebugField::Equal |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugField::Equal
helpviewer_keywords:
- IDebugField::Equal method
ms.assetid: 75369fe6-ddd3-497d-80d1-2488e6100e9f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1ae30cd36d2a3f51b697afa3cb5f4615a5f322da
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49830777"
---
# <a name="idebugfieldequal"></a>IDebugField::Equal
此方法将此字段与指定字段相等进行比较。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Equal(   
   IDebugField* pField  
);  
```  
  
```csharp  
int Equal(  
   IDebugField pField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pField`  
 [in]要与此比较的字段。  
  
## <a name="return-value"></a>返回值  
 如果字段是相同的则返回`S_OK`。 如果字段不同，返回`S_FALSE.`否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)