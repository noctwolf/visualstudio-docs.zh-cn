---
title: 'Idiaenumsegments:: Item |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Item method
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64089113f0ad5b0e3fea0189a5dc3bf680213158
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466339"
---
# <a name="idiaenumsegmentsitem"></a>IDiaEnumSegments::Item
通过索引中检索一个段。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD         index,  
   IDiaSegment** segment  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引的[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)要检索的对象。 索引是范围 0 到`count`-1，其中`count`返回[idiaenumsegments:: Get_count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)方法。  
  
 段  
 [out]返回[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)表示所需的段的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)