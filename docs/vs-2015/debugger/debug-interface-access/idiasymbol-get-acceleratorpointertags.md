---
title: IDiaSymbol::get_acceleratorPointerTags |Microsoft Docs
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
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efad3aeaf0d8a30d521d16612639d0b663ee8ebe
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720670"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

对 c + + AMP 快捷键存根 （stub） 函数返回对应的所有快捷键指针标记值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>参数  
 `cnt`  
 [in]输出数组的大小`pPointerTags`。  
  
 `pcnt`  
 [out]在 c + + AMP 快捷键存根 （stub） 函数中使用加速器指针标记的计数。  
  
 `pPointerTags`  
 [out]一个`DWORD`填入中 c + + AMP 快捷键存根 （stub） 函数的加速器指针标记值的数组指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="remarks"></a>备注  
 在调用此方法`IDiaSymbol`对应于 c + + AMP 快捷键存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



