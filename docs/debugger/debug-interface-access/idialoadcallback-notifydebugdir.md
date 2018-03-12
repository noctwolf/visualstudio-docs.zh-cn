---
title: "Idialoadcallback:: Notifydebugdir |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: fad37acafae21c6e82839979360f4ed9574aef1a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
当在.exe 文件中找到一个调试目录时调用。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT NotifyDebugDir (   
   BOOL  fExecutable,  
   DWORD cbData,  
   BYTE  data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fExecutable`  
 [in]`TRUE`如果的调试目录读取从可执行文件 （而不是.dbg 文件）。  
  
 `cbData`  
 [in]调试目录中的数据的字节数。  
  
 `data[]`  
 [in]使用的调试目录填充数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 通常忽略返回代码。  
  
## <a name="remarks"></a>备注  
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法调用此回调，在处理的可执行文件时找到的调试目录时。  
  
 此方法中删除客户端进行反向工程的可执行文件和/或调试文件需要支持以外的.pdb 文件中找到的调试信息。 借助此数据，客户端可以识别的调试信息可用类型和它位于可执行文件或.dbg 文件。  
  
 大多数客户端不需要此回调，因为`IDiaDataSource::loadDataForExe`方法以透明方式打开时提供符号所需的.pdb 和.dbg 文件。  
  
## <a name="see-also"></a>请参阅  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)