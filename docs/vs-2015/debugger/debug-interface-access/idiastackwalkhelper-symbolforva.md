---
title: 'Idiastackwalkhelper:: Symbolforva |Microsoft Docs'
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
- IDiaStackWalkHelper::symbolForVA method
ms.assetid: 8dd9455d-d44c-4dd6-a0aa-31131cbea2aa
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1c7b77429e265b1a9424db7e6d11161da27eb89b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51775727"
---
# <a name="idiastackwalkhelpersymbolforva"></a>IDiaStackWalkHelper::symbolForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索包含指定的虚拟地址的符号。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT symbolForVA(   
   ULONGLONG     va,  
   IDiaSymbol**  ppSymbol  
);  
```  
  
#### <a name="parameters"></a>参数  
 `va`  
 [in]包含请求的符号中的虚拟地址。 该符号必须是`SymTagFunctionType`(取值[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)枚举)。  
  
 `ppSymbol`  
 [out][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示指定地址处的符号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



