---
title: "Idiasession:: Put_loadaddress |Microsoft 文档"
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
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f4721ee818c4dc75d883c7accd2faa162521de13
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
在此符号存储区中将对应的可执行文件的负载地址设置为符号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `NewVal`  
 [in]加载的可执行文件的地址。  
  
## <a name="remarks"></a>备注  
 使用此方法的值计算符号虚拟地址 (VA) 属性。 除非此属性设置为非零值，才会计算虚拟地址。  
  
> [!NOTE]
>  你必须调用此方法，当您获取[IDiaSession](../../debugger/debug-interface-access/idiasession.md)对象，并在开始操作之前使用的对象，如果你需要使用符号上的任何虚拟属性。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)