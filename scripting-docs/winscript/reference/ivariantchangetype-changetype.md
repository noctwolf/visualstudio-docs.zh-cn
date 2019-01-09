---
title: IVariantChangeType::ChangeType |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IVariantChangeType.ChangeType
apilocation:
- scrobj.dll
helpviewer_keywords:
- IVariantChangeType::ChangeType
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a02b8a3991ff6d20370cd4a2ea4cd87aa9a1226
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086575"
---
# <a name="ivariantchangetypechangetype"></a>IVariantChangeType::ChangeType
采用变量值并创建具有指定类型的新变体。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pvarDst`  
 [in、 out]以包含所表示的值的变体`pvarSrc`，但指定的类型与`vtNew`。  
  
 `pvarSrc`  
 [in]要将更改为新类型的变体值。  
  
 `lcid`  
 [in]要转换到或从字符串自变量时使用的区域设置上下文。  
  
 `vtNew`  
 [in]指定的类型`pvarDst`成为。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 `pvarDst`和`pvarSrc`参数可能是相等的在这种情况下会覆盖原始值。 此方法将传递`pvarDst`到`VariantClear`函数，并由此`pvarDst`应为有效的值进行初始化。  
  
## <a name="see-also"></a>请参阅  
 [IVariantChangeType 接口](../../winscript/reference/ivariantchangetype-interface.md)