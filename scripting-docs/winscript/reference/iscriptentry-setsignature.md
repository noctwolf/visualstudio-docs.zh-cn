---
title: IScriptEntry::SetSignature |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetSignature
ms.assetid: 8513587d-9df2-4621-afe7-56eacbb5e688
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 660f667d3542ff2cb9a7e96444d98b3082218a2a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089500"
---
# <a name="iscriptentrysetsignature"></a>IScriptEntry::SetSignature
设置类型信息`IScriptEntry`函数对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetSignature(  
   ITypeInfo          *pti  
   ULONG              iMethod  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pti`  
 [in]类型的信息。  
  
 `iMethod`  
 [in]中的方法索引`ITypeInfo`对象。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 使用设置类型信息`IScriptEntry::SetSignature`或[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)。 此外可以通过基于内部函数表示形式的条目生成类型信息。  
  
## <a name="see-also"></a>请参阅  
 [IScriptEntry 接口](../../winscript/reference/iscriptentry-interface.md)