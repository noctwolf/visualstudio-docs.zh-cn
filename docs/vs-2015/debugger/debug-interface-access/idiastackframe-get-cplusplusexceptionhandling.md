---
title: 'Idiastackframe:: Get_cplusplusexceptionhandling |Microsoft Docs'
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
- IDiaStackFrame::get_cplusplusExceptionHandling method
ms.assetid: f2631820-c986-40ca-b61e-230d7a9c426c
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 55fbcb7d6a50e4021c070c2fd6971d21f1f767e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482647"
---
# <a name="idiastackframegetcplusplusexceptionhandling"></a>IDiaStackFrame::get_cplusplusExceptionHandling
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiastackframe:: Get_cplusplusexceptionhandling](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling)。  
  
检索一个标志，指示 c + + 异常处理有效。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_cplusplusExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果 c + + 异常处理有效此帧中; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果不支持的属性。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 C + + 异常处理不是结构化相同或系统异常处理。  
  
 若要确定如果结构化异常处理的有效方法是，调用[IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_systemExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling.md)



