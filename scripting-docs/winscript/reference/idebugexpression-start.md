---
title: IDebugExpression::Start |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.Start
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::Start
ms.assetid: a7af3470-62b5-40f0-987d-63b6b22538b3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c0d7b809f18407bfeb3de59c9cbb6e6e26911ad
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093335"
---
# <a name="idebugexpressionstart"></a>IDebugExpression::Start
开始表达式的计算。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Start(  
   IDebugExpressionCallBack*  pdecb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdecb`  
 [in]指示表达式计算过程何时完成的回调。 如果此参数为`NULL`，不触发任何事件，并且客户端必须使用轮询表达式状态`QueryIsComplete`。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法首先计算表达式。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)   
 [IDebugExpression 接口](../../winscript/reference/idebugexpression-interface.md)