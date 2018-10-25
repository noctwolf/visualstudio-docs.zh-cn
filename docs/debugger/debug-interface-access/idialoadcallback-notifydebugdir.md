---
title: 'Idialoadcallback:: Notifydebugdir |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdceb0f1f07a3ef9d22dbd30a02b2558c4d81603
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950870"
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
当在.exe 文件中发现的调试目录时调用。  
  
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
 [in]`TRUE`如果从可执行文件 （而非.dbg 文件） 中读取的调试目录。  
  
 `cbData`  
 [in]中的调试目录数据的字节数。  
  
 `data[]`  
 [in]使用的调试目录填充的数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回代码通常被忽略。  
  
## <a name="remarks"></a>备注  
 [Idiadatasource:: Loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)方法处理的可执行文件时找到调试目录时将调用此回调。  
  
 此方法删除客户端进行反向工程，可执行文件和/或调试文件需要支持以外的.pdb 文件中找到的调试信息。 使用此数据，客户端可以识别可用的调试信息的类型和它位于可执行文件或.dbg 文件。  
  
 大多数客户端不需要此回调，因为`IDiaDataSource::loadDataForExe`方法以透明方式打开时需提供符号的.pdb 和.dbg 文件。  
  
## <a name="see-also"></a>请参阅  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)