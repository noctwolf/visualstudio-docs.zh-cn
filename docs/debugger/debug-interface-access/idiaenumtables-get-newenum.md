---
title: 'Idiaenumtables:: Get__newenum |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::get__NewEnum method
ms.assetid: 7b1159c7-a5f0-4baa-861a-dc11437d8b93
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9a29c91159855901a2c2b0666b21830d7eac1d5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumtablesgetnewenum"></a>IDiaEnumTables::get__NewEnum
检索<xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT>的此枚举器的版本。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get__NewEnum (   
   IUnknown** pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`IUnknown`表示接口<xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT>的此枚举器的版本。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)