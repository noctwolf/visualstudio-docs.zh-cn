---
title: IActiveScriptStats::GetStatEx | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.GetStatEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStatEx
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5f1585e335fac0072eba48494bf8c27736a47f41
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149164"
---
# <a name="iactivescriptstatsgetstatex"></a>IActiveScriptStats::GetStatEx
返回自定义脚本统计信息。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guid`  
 [in]指定要返回的统计信息。 语义的统计信息对应于特定 GUID 是完全定义的引擎。  
  
 `pluHi`  
 [out]表示统计信息的 64 位无符号整数的高 32 位。  
  
 `pluLo`  
 [out]表示统计信息的 64 位无符号整数的低 32 位。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_NOTIMPL`|未实现方法。|  
  
## <a name="remarks"></a>备注  
 此方法允许自定义脚本引擎返回统计信息的自定义主机到有意义。  
  
> [!NOTE]
>  目前尚未实现此方法。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats 接口](../../winscript/reference/iactivescriptstats-interface.md)