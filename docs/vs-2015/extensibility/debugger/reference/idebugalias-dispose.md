---
title: IDebugAlias::Dispose |Microsoft Docs
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
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c6032612d021e257a9f2c8ef74d35f3bec4a343a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471435"
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugAlias::Dispose](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugalias-dispose)。  
  
将标记为删除此别名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Dispose();  
```  
  
```csharp  
int Dispose();  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 一旦调用此方法，该别名不再可用。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

