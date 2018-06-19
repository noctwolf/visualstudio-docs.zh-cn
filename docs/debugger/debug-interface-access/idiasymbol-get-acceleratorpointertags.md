---
title: IDiaSymbol::get_acceleratorPointerTags |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24db7164335a8deffbac7cb4f62207a974f6efb9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460666"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
对 c + + AMP 快捷键存根 （stub） 函数返回对应的所有快捷键指针标记值。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>参数  
 `cnt`  
 [in]输出数组的大小`pPointerTags`。  
  
 `pcnt`  
 [out]C + + AMP 快捷键存根 （stub） 函数中的加速器指针标记计数。  
  
 `pPointerTags`  
 [out]A`DWORD`用 c + + AMP 快捷键存根 （stub） 函数中的加速器指针标记值填充的数组指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="remarks"></a>备注  
 在调用此方法`IDiaSymbol`对应于 c + + AMP 快捷键存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)