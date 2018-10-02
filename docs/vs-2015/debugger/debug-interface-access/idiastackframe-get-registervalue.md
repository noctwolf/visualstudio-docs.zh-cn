---
title: 'Idiastackframe:: Get_registervalue |Microsoft Docs'
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
- IDiaStackFrame::get_registerValue method
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 496d15d8bfed0fc6d674e09a2bc9046788e11ca1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480736"
---
# <a name="idiastackframegetregistervalue"></a>IDiaStackFrame::get_registerValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiastackframe:: Get_registervalue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-registervalue)。  
  
检索指定寄存器的值，如存储在堆栈帧。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_registerValue(  
   ULONG      registerIndex,  
   ULONGLONG *pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `registerIndex`  
 [in]之一[CV_HREG_e 枚举](../../debugger/debug-interface-access/cv-hreg-e.md)枚举值。  
  
 `pRetVal`  
 [out]存储在寄存器的值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为将返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [CV_HREG_e 枚举](../../debugger/debug-interface-access/cv-hreg-e.md)



