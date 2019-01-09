---
title: IDebugApplication::CreateApplicationNode |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.CreateApplicationNode
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::CreateApplicationNode
ms.assetid: 1a1414f6-df14-4c56-b39a-8384cf16174a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 71aea5c3a7efb6534daab5fc916187c0f56122b3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095545"
---
# <a name="idebugapplicationcreateapplicationnode"></a>IDebugApplication::CreateApplicationNode
创建一个新的应用程序节点与特定文档提供程序相关联。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT CreateApplicationNode(  
   IDebugApplicationNode**  ppdanNew  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppdanNew`  
 [out]与此文档提供程序关联的应用程序节点。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 新的应用程序节点不可见，直到它附加到父节点。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)