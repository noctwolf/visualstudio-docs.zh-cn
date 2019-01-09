---
title: ISetNextStatement::CanSetNextStatement |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- ISetNextStatement.CanSetNextStatement
apilocation:
- scrobj.dll
ms.assetid: e2a54634-31ec-4d16-84e8-2b123845d876
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5288b0cffc3b8bfca0e995e67d4b3e4bf3a6b2e2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090124"
---
# <a name="isetnextstatementcansetnextstatement"></a>ISetNextStatement::CanSetNextStatement
此方法确定是否执行点，用于确定要执行的代码的下一个语句，可以将设置为指定的位置。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT CanSetNextStatement(  
   IDebugStackFrame*  pStackFrame,  
   IDebugCodeContext*  pCodeContext  
)  
```  
  
#### <a name="parameters"></a>参数  
 `pStackFrame`  
 [in]指向堆栈帧对象的指针。  
  
 `pCodeContext`  
 [in]对代码上下文对象的指针。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|下一条语句可以将更新为指定的代码上下文。|  
|`S_FALSE`|下一条语句不能更新为指定的代码上下文。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [ISetNextStatement 接口](../../winscript/reference/isetnextstatement-interface.md)