---
title: ISimpleConnectionPoint::Advise |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISimpleConnectionPoint.Advise
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::Advise
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3c0ea37e6fabb051458a11c4838061126bd98bf
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091736"
---
# <a name="isimpleconnectionpointadvise"></a>ISimpleConnectionPoint::Advise
建立简单连接点对象和客户端的接收器之间的连接。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdisp`  
 [in]指向`IDispatch`接口在客户端上的通知接收器。 客户端的接收器从简单的连接点接收传出调用。  
  
 `pdwCookie`  
 [out]指向返回的令牌，用于唯一标识此连接。 调用方在更高版本使用此令牌来将其传递到删除连接`ISimpleConnectionPoint::Unadvise`方法。 如果未成功建立连接，此值为零。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法会建立简单连接点对象和客户端的接收器之间的连接。  
  
## <a name="see-also"></a>请参阅  
 [ISimpleConnectionPoint 接口](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)