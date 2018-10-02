---
title: 'Idiasymbol:: Get_backendbuild |Microsoft Docs'
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
- IDiaSymbol::get_backEndBuild method
ms.assetid: 423af497-9294-438e-92b4-456c6f56dc56
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8c3577d809e28f448f807616852f7baf447705f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482123"
---
# <a name="idiasymbolgetbackendbuild"></a>IDiaSymbol::get_backEndBuild
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiasymbol:: Get_backendbuild](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-backendbuild)。  
  
检索编译器后端内部版本号。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_backEndBuild (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回的后端内部版本号。 请参阅“备注”。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 编译器通常组成两个主要元素： 前端 （分析器），这将其处理为中间格式分析的源代码和一个后端 （代码生成器），后者将中间格式转换到程序集。 不常见的前端具有后端的版本不同。  
  
 前端或后端的版本号三个部分组成：\<主要 >。\<次要 >。\<生成 >，其中\<主要 > 是主版本号，\<次要 > 是的次版本号和\<生成 > 是生成号。 例如，13.10.3077。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v7.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



