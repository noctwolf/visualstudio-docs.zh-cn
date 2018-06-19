---
title: 'Idiasession:: Put_loadaddress |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0b04db800e5b61ef1598fe4c81a9ab362e375e3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31462641"
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