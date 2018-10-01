---
title: IDebugDefaultPort2::GetPortNotify |Microsoft Docs
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
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0a0cd508f0eab1d4ffc0feea32de128c411bef6c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478226"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugDefaultPort2::GetPortNotify](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdefaultport2-getportnotify)。  
  
此方法获取[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)接口为此端口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppPortNotify`  
 [out][IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，`QueryInterface`对象，实现上调用方法[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)接口，以获得[IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)接口。 但是，有一些情况下在不同的对象实现所需的接口。 此方法会隐藏这种情况，并返回`IDebugPortNotify2`中最合适的对象的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)

