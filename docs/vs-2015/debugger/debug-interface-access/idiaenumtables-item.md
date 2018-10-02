---
title: 'Idiaenumtables:: Item |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea80cbcda60b54f17e79e492c43058579465ad90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479820"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumtables:: Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumtables-item)。  
  
检索通过索引或名称的表。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>参数  
 `index`  
 [in]索引或名称[IDiaTable](../../debugger/debug-interface-access/idiatable.md)要检索。 如果使用整数变量，则它必须是介于 0 到`count`-1，其中`count`与返回的[idiaenumtables:: Get_count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)方法。  
  
 `table`  
 [out]返回[IDiaTable](../../debugger/debug-interface-access/idiatable.md)对象，表示所需的表。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果指定的字符串变体，则该字符串命名为特定表。 该名称应是表名称之一中定义[常量 (调试接口访问 SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)。  
  
## <a name="example"></a>示例  
  
```cpp#  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiaenumtables:: Get_count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [常量（调试接口访问 SDK）](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)



