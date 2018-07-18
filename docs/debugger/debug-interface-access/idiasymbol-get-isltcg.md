---
title: 'Idiasymbol:: Get_isltcg |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isLTCG method
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a799cf16dbf603f75cd810f9c249f4c0e8ba49ec
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464753"
---
# <a name="idiasymbolgetisltcg"></a>IDiaSymbol::get_isLTCG
检索一个标志，指定是否[编译单位](../../debugger/debug-interface-access/compiland.md)已经链接，链接器开关[/LTCG （链接时间代码生成）](/cpp/build/reference/ltcg-link-time-code-generation)，这样有助于全程序优化。 此交换机仅适用于托管代码。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>参数  
 pFlag  
 [out]返回`TRUE`如果`compiland`已链接使用 /LTCG 链接器开关; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v8.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)