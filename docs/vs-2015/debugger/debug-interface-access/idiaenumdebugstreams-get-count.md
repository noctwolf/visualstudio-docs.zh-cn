---
title: 'Idiaenumdebugstreams:: Get_count |Microsoft Docs'
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
helpviewer_keywords:
- IDiaEnumDebugStreams::get_Count method
ms.assetid: 5c13fa9a-b35e-47b0-806f-1f53bfe1ba89
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b3fa987d03dc99adee9680029866fbfb05b2ec8c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481921"
---
# <a name="idiaenumdebugstreamsgetcount"></a>IDiaEnumDebugStreams::get_Count
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumdebugstreams:: Get_count](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumdebugstreams-get-count)。  
  
检索调试流的数量。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_Count(   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回此枚举器中可用的调试流的数量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)   
 [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)



