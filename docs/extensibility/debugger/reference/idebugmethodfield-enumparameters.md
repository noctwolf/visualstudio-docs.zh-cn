---
title: "IDebugMethodField::EnumParameters |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumParameters
helpviewer_keywords: IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f60fbde074f660647aedd65a7bae7f98576d485d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
创建方法的参数的枚举数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppParams`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)表示对方法的参数列表的对象; 否则，返回 null 值，如果任何参数。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK，则返回 S_FALSE，如果任何参数。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 每个元素都[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示不同类型的参数对象。 调用[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)要确定哪种类型的参数对象表示完全每个对象的方法。  
  
 参数包含两个其变量名称和其类型。 对类方法的第一个参数通常是"this"指针。  
  
 如果仅在需要的参数类型，才调用[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)