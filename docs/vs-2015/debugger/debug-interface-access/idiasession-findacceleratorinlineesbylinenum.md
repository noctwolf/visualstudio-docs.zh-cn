---
title: IDiaSession::findAcceleratorInlineesByLinenum |Microsoft Docs
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
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 99f344a1f6de8dba9dc14d1720515319796f629f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480437"
---
# <a name="idiasessionfindacceleratorinlineesbylinenum"></a>IDiaSession::findAcceleratorInlineesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaSession::findAcceleratorInlineesByLinenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findacceleratorinlineesbylinenum)。  
  
返回指定的源位置相对应的内嵌帧的符号的枚举。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `parent`  
 [in]`IDiaSymbol` ，对应于需要搜索的加速器存根 （stub） 函数。  
  
 `file`  
 [in]`IDiaSourceFile`的源位置。  
  
 `linenum`  
 [in]源位置的行数。  
  
 `colnum`  
 [in]源位置的列数。  
  
 `ppResult`  
 [out]一个指向`IDiaEnumLineNumbers`使用结果初始化的接口指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



