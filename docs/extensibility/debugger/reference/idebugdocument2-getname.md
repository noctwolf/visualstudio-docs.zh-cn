---
title: IDebugDocument2::GetName |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDocument2::GetName
helpviewer_keywords:
- IDebugDocument2::GetName
ms.assetid: 6f09ff09-b0cf-4472-8fc8-143991f0ceb1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e1c819c63a40a1d7f08b46b67a8cfd2c1949c074
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49905202"
---
# <a name="idebugdocument2getname"></a>IDebugDocument2::GetName
获取文档的名称中有几种形式之一。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName(   
   GETNAME_TYPE gnType,  
   BSTR*        pbstrFileName  
);  
```  
  
```csharp  
int GetName(   
   enum_GETNAME_TYPE gnType,  
   out string        pbstrFileName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `gnType`  
 [in]中的值[GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)枚举，用于确定要返回名称的类型。  
  
 `pbstrFileName`  
 [out]返回包含文档名称的字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 作为一个标题或文件的名称或甚至文件名称的一部分，此方法可以例如，返回的文档的名称。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md)   
 [GETNAME_TYPE](../../../extensibility/debugger/reference/getname-type.md)