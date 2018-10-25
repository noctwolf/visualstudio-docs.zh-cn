---
title: IDebugDefaultPort2::QueryIsLocal |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2ed411d632df544d47b376e59bc59b7331d8aa91
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49901796"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
此方法确定此端口是否在本地计算机上。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`此端口是在本地 （在调用方所在的计算机） 或`S_FALSE`如果端口是在另一台计算机上。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)