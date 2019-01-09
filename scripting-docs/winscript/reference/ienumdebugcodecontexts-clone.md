---
title: IEnumDebugCodeContexts::Clone |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugCodeContexts.Clone
apilocation:
- jscript.dll
helpviewer_keywords:
- IEnumDebugCodeContexts::Clone
ms.assetid: eaad6af9-4a0a-49c9-8f73-bccaa42b235c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bdf003c73dd6f98f6f102f3b7dd36b1d69a522c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089526"
---
# <a name="ienumdebugcodecontextsclone"></a>IEnumDebugCodeContexts::Clone
创建一个包含与当前枚举数相同的状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Clone(  
   IEnumDebugCodeContexts**  ppescc  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppescc`  
 [out]返回`IEnumDebugCodeContexts`接口的枚举器的克隆。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法创建一个包含与当前枚举数相同的状态的枚举器。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugCodeContexts 接口](../../winscript/reference/ienumdebugcodecontexts-interface.md)