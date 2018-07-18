---
title: 'Idiareadexeatrvacallback:: Readexecutableatrva |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f71db30a3e4cba957e6aba0981587276af714e3e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461958"
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
读取指定的开始的指定相对虚拟地址 (RVA) 从可执行文件的字节数。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT ReadExecutableAtRVA (   
   DWORD  relativeVirtualAddress,  
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `relativeVirtualAddress`  
 [in]可执行文件中开始读取 RVA。  
  
 `cbData`  
 [in]要读取的字节数。  
  
 `pcbData`  
 [out]返回读取的字节数。  
  
 `data[]`  
 [在中，out]使用从文件中读取的字节填充数组。  
  
## <a name="remarks"></a>备注  
 若要从使用的相对虚拟地址的可执行文件加载数据字节的 DIA 支持代码通过调用此方法。 此方法称为 support 的[idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)