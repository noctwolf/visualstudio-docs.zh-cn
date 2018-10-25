---
title: 'Idiasymbol:: Get_symtag |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_symTag method
ms.assetid: 139a35bd-faeb-4878-be72-394dedfbb18f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 346bfe7b0d096a9658e5063d97337349cc6a1a04
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49887938"
---
# <a name="idiasymbolgetsymtag"></a>IDiaSymbol::get_symTag
检索符号类型分类器。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_symTag (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回一个值从[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)枚举，用于指定符号类型分类器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="example"></a>示例  
  
```C++  
IDiaSymbol* pType;  
DWORD       tag = 0;  
pType->get_symTag( &tag );  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)