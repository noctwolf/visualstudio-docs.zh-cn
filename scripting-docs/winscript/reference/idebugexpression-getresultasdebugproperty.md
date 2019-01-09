---
title: IDebugExpression::GetResultAsDebugProperty |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.GetResultAsDebugProperty
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::GetResultAsDebugProperty
ms.assetid: 9075bf2f-d5bb-464e-b6c2-3fa3215e9ae0
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6aebe983c33416d1c3d12d18c272fd1e4de27467
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093101"
---
# <a name="idebugexpressiongetresultasdebugproperty"></a>IDebugExpression::GetResultAsDebugProperty
返回表达式计算作为一种调试属性和操作的返回值的结果。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetResultAsDebugProperty(  
   HRESULT*          phrResult,  
   IDebugProperty**  ppdp  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phrResult`  
 [out]操作的返回值。  
  
 `ppdp`  
 [out]表达式调试属性。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_PENDING`|该操作仍是挂起。|  
  
## <a name="remarks"></a>备注  
 此方法返回作为表达式计算的结果`IDebugProperty`和操作的`HRESULT`。  
  
 此方法返回`S_OK`并`phrResult`返回`E_ABORT`如果`Abort`中止操作。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExpression 接口](../../winscript/reference/idebugexpression-interface.md)   
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)