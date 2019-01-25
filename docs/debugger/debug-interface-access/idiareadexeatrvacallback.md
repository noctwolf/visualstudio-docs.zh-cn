---
title: IDiaReadExeAtRVACallback |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e00ce2e1286c2309a11984f9bde23aa74071a076
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859287"
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
允许客户端应用程序提供的可执行文件的相对虚拟地址由指定的字节数。  
  
## <a name="syntax"></a>语法  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDiaReadExeAtRVACallback`。  
  
|方法|说明|  
|------------|-----------------|  
|[IDiaReadExeAtRVACallback::ReadExecutableAtRVA](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|读取指定的开始的指定相对虚拟地址 (RVA) 从可执行文件的字节数。|  
  
## <a name="remarks"></a>备注  
 客户端应用程序实现此接口以提供到可执行文件的文件中使用的相对虚拟地址的可执行文件的字节。 若要使用绝对文件偏移量，实现[IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此方法是由客户端应用程序实现并传递给[idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法作为一种方法来读取文件。  
  
## <a name="requirements"></a>要求  
 标头：dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>请参阅  
 [接口（调试接口访问 SDK）](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)