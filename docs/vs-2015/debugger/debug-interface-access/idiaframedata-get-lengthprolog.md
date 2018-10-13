---
title: 'Idiaframedata:: Get_lengthprolog |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 320699fd4d8cddcba8765758b23b61b942695fd4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223920"
---
# <a name="idiaframedatagetlengthprolog"></a>IDiaFrameData::get_lengthProlog
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索块中的序言代码的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_lengthProlog (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回的序言代码的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 序言代码是一系列的说明，可以保留寄存器、 设置的 CPU 的状态，并建立函数的堆栈。  
  
## <a name="see-also"></a>请参阅  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



