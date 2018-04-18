---
title: IDiaPropertyStorage::ReadPropertyNames |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1624e3577128556a098f96fd41c9ba1dc1eb84e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
检索对应的字符串名称给定属性标识符。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cpropid`  
 [in]中的属性 id 数`rgpropid`。  
  
 `rgpropid`  
 [in]要为其获取名称的属性 id 的数组 (`PROPID`作为 WTypes.h 中定义`ULONG`)。  
  
 `rglpwstrName`  
 [在中，out]指定的属性 id 的属性名称的数组。 该数组必须是预分配，以容纳的属性名称请求的数，并且必须能够以容纳至少`cpropid``BSTR`字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 返回的属性名称必须被释放 (通过调用`SysFreeString`函数) 它们不再需要时。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)