---
title: IDebugPortSupplier2::CanAddPort |Microsoft 文档
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
ms.openlocfilehash: 00b1c1303be8ccc326a58a20d132ad38db3b426d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113957"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
验证端口供应商可以添加新端口。  
  
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
 如果可以添加端口，则返回`S_OK`; 否则为返回`S_FALSE`以指示无端口可以添加到此端口供应商。  
  
## <a name="remarks"></a>备注  
 调用此方法之前调用[添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)由于后一种方法将创建该端口，以及添加它，这可能会耗时的操作的方法。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [添加](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)