---
title: IDebugPortSupplier2::CanAddPort |Microsoft Docs
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
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1478841e6fdd48a6c956486153db7bf4e81435fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468814"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugPortSupplier2::CanAddPort](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier2-canaddport)。  
  
验证端口提供程序可以添加新端口。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

