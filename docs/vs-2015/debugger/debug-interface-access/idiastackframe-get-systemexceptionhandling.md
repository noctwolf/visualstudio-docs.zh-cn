---
title: IDiaStackFrame::get_systemExceptionHandling |Microsoft Docs
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
- IDiaStackFrame::get_systemExceptionHandling
ms.assetid: c76cf265-dea0-4159-883f-32b50bbef044
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bb19a46b2be346c956f5877068283f8b6007b78
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484306"
---
# <a name="idiastackframegetsystemexceptionhandling"></a>IDiaStackFrame::get_systemExceptionHandling
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaStackFrame::get_systemExceptionHandling](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackframe-get-systemexceptionhandling)。  
  
检索一个标志，指示系统异常处理是否生效。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果系统异常处理有效此帧中; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果不支持的属性。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 系统异常处理也称为是结构化的异常处理。 这不是与 c + + 异常处理相同的功能。  
  
 若要确定是否有效 c + + 异常处理，请调用[idiastackframe:: Get_cplusplusexceptionhandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)



