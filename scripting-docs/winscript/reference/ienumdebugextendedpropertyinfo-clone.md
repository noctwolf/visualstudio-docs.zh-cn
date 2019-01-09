---
title: IEnumDebugExtendedPropertyInfo::Clone |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IEnumDebugExtendedPropertyInfo.Clone
apilocation:
- scrobj.dll
helpviewer_keywords:
- IEnumDebugExtendedPropertyInfo::Clone
ms.assetid: dd645cf6-bfb3-486c-829e-bb91a6639665
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1d58419783d4f101a6018fe00d9c9a4ddc94548
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093816"
---
# <a name="ienumdebugextendedpropertyinfoclone"></a>IEnumDebugExtendedPropertyInfo::Clone
创建一个包含当前枚举数形式的相同枚举状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Clone (  
   IEnumDebugExtendedPropertyInfo** ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回克隆`IEnumDebugExtendedPropertyInfo`接口。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugExtendedPropertyInfo 接口](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)