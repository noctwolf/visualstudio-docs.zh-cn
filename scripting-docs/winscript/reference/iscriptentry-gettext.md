---
title: IScriptEntry::GetText |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetText
ms.assetid: 105b8244-1972-4b39-ac18-965f1f345ef2
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a01d6df1281a32fee435c80465f148fcc7436a3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096416"
---
# <a name="iscriptentrygettext"></a>IScriptEntry::GetText
返回对应的文本`IScriptEntry`脚本块中或包含在源代码`IScriptScriptlet`事件处理程序。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetText(  
   BSTR               *pbstr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstr`  
 [out]中的文本`IScriptEntry`脚本块中或包含在源代码`IScriptScriptlet`事件处理程序。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptEntry 接口](../../winscript/reference/iscriptentry-interface.md)