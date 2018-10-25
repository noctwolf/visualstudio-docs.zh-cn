---
title: 'Idiaenumframedata:: Item |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Item method
ms.assetid: 2761a72d-1868-4f5b-a32e-c2a1d9358c91
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c15d0dec0ccaa20e2fcf59f88d68d5febc63eb04
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49887394"
---
# <a name="idiaenumframedataitem"></a>IDiaEnumFrameData::Item
通过索引中检索帧数据元素。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD           index,  
   IDiaFrameData** section  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)要检索对象。 索引是 0 到范围内`count`-1，其中`count`返回的[idiaenumframedata:: Get_count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)方法。  
  
 section  
 [out]返回[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)对象，表示所需的帧数据元素。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)