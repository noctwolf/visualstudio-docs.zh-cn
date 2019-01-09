---
title: IScriptEntry::SetItemName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetItemName
ms.assetid: 9551a7ec-38f8-466a-9722-09367763f380
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20af0975a4175d10b110ac5e3cef9e0055f4ce1b
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097755"
---
# <a name="iscriptentrysetitemname"></a>IScriptEntry::SetItemName
设置标识的项名称`IScriptEntry`对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>参数  
 `psz`  
 [in]包含的项名称的缓冲区的地址。 主机使用的项名称来标识该项。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_FAIL`|该方法未成功。|  
  
## <a name="remarks"></a>备注  
 有关`IScriptEntry`对象，此方法返回`S_OK`。  
  
 有关`IScriptScriptlet`对象 (从其派生`IScriptEntry`)，此方法返回`E_FAIL`。 有关`IScriptScriptlet`对象，通过设置项目名称[IActiveScriptAuthor::AddScriptlet](../../winscript/reference/iactivescriptauthor-addscriptlet.md) ，并且不能更改。  
  
## <a name="see-also"></a>请参阅  
 [IScriptEntry 接口](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)