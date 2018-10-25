---
title: IDebugProperty::GetExtendedInfo |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugProperty.GetExtendedInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugProperty::GetExtendedInfo
ms.assetid: a989ade5-16d5-4ee6-8d8a-8dcbfad24034
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c66ea53bde17f2936567cd93ae0be166f35382ed
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49925534"
---
# <a name="idebugpropertygetextendedinfo"></a>IDebugProperty::GetExtendedInfo
获取扩展的属性信息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetExtendedInfo (  
   ULONG  cInfos,  
   GUID*  rgguidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cInfos`  
 [in]扩展的信息对象的计数。  
  
 `rgguidExtendedInfo`  
 [in]一个数组`GUID`s 传递，以便可以在同一时间检索多个项的扩展信息。  
  
 `pExtendedInfo`  
 [out]返回一个数组`VARIANT`s 可用于检索的扩展的属性信息。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。  
  
## <a name="remarks"></a>备注  
 此接口获取扩展此对象的信息。 API 存在唯一目的是检索不会将自身添加到通过使用要检索的信息为了`IDebugProperty::GetPropertyInfo`)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty 接口](../../winscript/reference/idebugproperty-interface.md)