---
title: 'Idiasession:: Findinjectedsource |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a16e3827999d165f0d04b803e4d0611bf4f2538d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851990"
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
检索已放置到符号存储区的属性提供者的源列表或在编译过程的其他组件。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findInjectedSource (   
   LPCOLESTR                 srcFile,  
   IDiaEnumInjectedSources** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 srcFile  
 [in]要搜索的源文件的名称。  
  
 ppResult  
 [out]返回[IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)对象，其中包含所有的插入源的列表。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)