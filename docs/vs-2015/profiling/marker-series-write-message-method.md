---
title: 'marker_series:: write_message 方法 | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::marker_series::write_message
helpviewer_keywords:
- Concurrency::diagnostic::marker_series::write_message method
ms.assetid: 546121bc-67e0-4a5a-a456-12bd78fd6de2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 98a91ca0a3484e35b8703da1efbd554fa70c84ad
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468984"
---
# <a name="markerserieswritemessage-method"></a>marker_series::write_message 方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[marker_series:: write_message 方法](https://docs.microsoft.com/visualstudio/profiling/marker-series-write-message-method)。  
  
向并发可视化工具跟踪文件写入一条消息。  
  
## <a name="syntax"></a>语法  
  
```  
void write_message(  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   marker_importance _Importance,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
void write_message(  
   marker_importance _Importance,  
   int _Category,  
   _In_ LPCTSTR _Format,  
   ...  
);  
```  
  
#### <a name="parameters"></a>参数  
 `_Format`  
 一个复合格式字符串，其中包含与零个或多个格式项混合的文本，这些格式项对应于参数列表中的对象。  
  
 `_Importance`  
 重要性级别。  
  
 `_Category`  
 类别.重要性级别。  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** Concurrency::diagnostic  
  
## <a name="see-also"></a>请参阅  
 [marker_series 类](../profiling/marker-series-class.md)



