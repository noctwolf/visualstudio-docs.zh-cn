---
title: IScriptEntry::SetName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetName
ms.assetid: dfa33450-87d7-4c8e-bfd8-0cc2d6542a0e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c7929d9d073e7b21030dcddc3db04abc977bdd3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086666"
---
# <a name="iscriptentrysetname"></a>IScriptEntry::SetName
对于表示单个对象 （如某个函数） 的条目，设置的对象的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>参数  
 `psz`  
 [in]新名称的`IScriptEntry`对象。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptEntry 接口](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)