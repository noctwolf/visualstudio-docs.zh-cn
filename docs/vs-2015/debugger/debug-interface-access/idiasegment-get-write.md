---
title: IDiaSegment::get_write | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSegment::get_write method
ms.assetid: 5fcda988-6be1-4b2f-8660-b59aa78fc35d
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9fb40262b194b8888a3fc4033cef18480ecb2439
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58926014"
---
# <a name="idiasegmentgetwrite"></a>IDiaSegment::get_write
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索一个标志，指示是否可以修改段。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_write (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果段可写; 否则为返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
