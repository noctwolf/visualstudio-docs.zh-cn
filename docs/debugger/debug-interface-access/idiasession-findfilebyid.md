---
title: 'Idiasession:: Findfilebyid |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed79b65823c3a777c13a90331468074347425ef5
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466716"
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
通过源文件标识符来检索源文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `uniqueId`  
 [in]指定的源文件标识符。  
  
 `ppResult`  
 [out]返回[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)检索表示源文件的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 源文件标识符是对 DIA SDK 在内部使用，以使所有源文件是唯一的唯一值。 此方法通常在内部用于 DIA SDK。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession:: Findfile](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)