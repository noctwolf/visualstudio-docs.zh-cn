---
title: IActiveScript::GetScriptState | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptState
ms.assetid: 59837f7c-755d-45c4-8194-bd57638fe2e1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a64067679e1c56831002494c579ffdeba84a1abe
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346626"
---
# <a name="iactivescriptgetscriptstate"></a>IActiveScript::GetScriptState
检索脚本引擎的当前的状态。 此方法可以从非基础线程调用不会导致到主机对象或一个非基本标注[IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)接口。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetScriptState(  
    SCRIPTSTATE *pss  // address of structure for state information  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pss`  
 [out]一个变量的地址来接收中定义的值[SCRIPTSTATE 枚举](../../winscript/reference/scriptstate-enumeration.md)枚举。 值指示调用线程与关联的脚本引擎的当前状态。  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`如果成功，或`E_POINTER`如果指定了无效的指针。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScript](../../winscript/reference/iactivescript.md)