---
title: IDiaSymbol::get_isAcceleratorStubFunction |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 69f82f836be6ab91fe73af5a0febf7a39723b191
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58932871"
---
# <a name="idiasymbolgetisacceleratorstubfunction"></a>IDiaSymbol::get_isAcceleratorStubFunction
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指示是否符号对应于顶层函数符号的着色器编译到相对应的快捷键`parallel_for_each`调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT get_isAcceleratorStubFunction(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>参数  
 `pFlag`  
 [out]一个指向`BOOL`，该值指示是否符号对应于顶层函数符号的着色器编译到相对应的快捷键`parallel_for_each`调用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
