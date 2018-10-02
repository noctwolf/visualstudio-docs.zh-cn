---
title: IDebugEnumField::GetUnderlyingSymbol |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEnumField::GetUnderlyingSymbol
helpviewer_keywords:
- IDebugEnumField::GetUnderlyingSymbol method
ms.assetid: c3b8a117-6708-4cfd-8ffc-5f007d706bc5
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 986032f7c4a3c26b361aab9b10e17e3b9045a49f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482943"
---
# <a name="idebugenumfieldgetunderlyingsymbol"></a>IDebugEnumField::GetUnderlyingSymbol
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugEnumField::GetUnderlyingSymbol](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol)。  
  
此方法返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示枚举的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetUnderlyingSymbol(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetUnderlyingSymbol(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述了此枚举的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举的名称还包含通过使用绑定到的内存位置的枚举类型[绑定](../../../extensibility/debugger/reference/idebugbinder-bind.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [Bind](../../../extensibility/debugger/reference/idebugbinder-bind.md)

