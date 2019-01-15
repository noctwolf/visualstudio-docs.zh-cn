---
title: 'Idiadatasource:: Opensession |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bea16f7ff0f723979ded9962a8ff9e620227f8ea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53843107"
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
将打开一个会话，用于查询符号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>参数  
 ppSession  
 [out]返回[IDiaSession](../../debugger/debug-interface-access/idiasession.md)对象，表示打开会话。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 下表显示了可能的此方法的返回值。  
  
|“值”|说明|  
|-----------|-----------------|  
|E_UNEXPECTED|[IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)对象之前尚未初始化了一个来源为符号。|  
|E_INVALIDARG|`ppSession` 参数无效。|  
|E_OUTOFMEMORY|内存不足，无法打开会话。|  
  
## <a name="remarks"></a>备注  
 此方法打开[IDiaSession](../../debugger/debug-interface-access/idiasession.md)数据源对象。  
  
 `IDiaSession` 对象中实现数据源的查询。 会话管理调试符号的每个集的一个地址空间。 如果数据源符号所描述的.exe 或.dll 文件是活动中多个地址范围 （例如，因为多个进程具有它加载），则应使用为每个地址范围的一个会话。  
  
## <a name="example"></a>示例  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [概述](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [查询 .Pdb 文件](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)