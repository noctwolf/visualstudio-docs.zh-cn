---
title: IRemoteDebugApplicationEx:SetLocale |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:SetLocale
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:SetLocale
ms.assetid: cd19f725-f4cd-453a-95e1-0bad676451da
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3565a966b74e6af18b2c397790fcd8d923e6bb15
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095701"
---
# <a name="iremotedebugapplicationexsetlocale"></a>IRemoteDebugApplicationEx:SetLocale
设置调试器本地化的语言。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetLocale(  
   DWORD  dwLangID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwLangID`  
 [in]语言 id。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [ISetNextStatement 接口](../../winscript/reference/isetnextstatement-interface.md)