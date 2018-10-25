---
title: IDebugPortSupplier2::CanAddPort |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7f4494aa41613f93396389176436dcf0c40be53
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49902303"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
验证端口提供程序可以添加新端口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>返回值  
 如果可以添加端口，则返回`S_OK`; 否则为返回`S_FALSE`以指示可以将任何端口添加到此端口提供程序。  
  
## <a name="remarks"></a>备注  
 调用此方法之前调用[端口](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)方法因为后一种方法创建该端口，以及添加它，这可能一个耗时的操作。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)