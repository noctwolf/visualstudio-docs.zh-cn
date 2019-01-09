---
title: IScriptScriptlet::SetSubItemName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptScriptlet.SetSubItemName
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptScriptlet::SetSubItemName
ms.assetid: 619f222f-b4c3-4c7b-9d19-e4e7037343a6
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 777a69e47ed7f88851cae0d20f2eb23ee6978296
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097705"
---
# <a name="iscriptscriptletsetsubitemname"></a>IScriptScriptlet::SetSubItemName
Scriptlet 的对象主机的完全限定名称中设置的最后一个标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetSubItemName(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>参数  
 `psz`  
 如果主机的完全限定 scriptlet 的名称有多个级别，`psz`是在第二个级别的标识符的缓冲区地址。  
  
 如果主机的完全限定 scriptlet 的名称有一个级别，`psz`是在第一个级别的标识符的缓冲区地址。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptScriptlet 接口](../../winscript/reference/iscriptscriptlet-interface.md)