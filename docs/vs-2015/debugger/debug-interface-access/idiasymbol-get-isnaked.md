---
title: 'Idiasymbol:: Get_isnaked |Microsoft Docs'
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
- IDiaSymbol::get_isNaked method
ms.assetid: b16629dc-8e17-476b-9c7b-58e7277c61ed
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1da5488995575b76529c8273fa4c42f70675d8cd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482072"
---
# <a name="idiasymbolgetisnaked"></a>IDiaSymbol::get_isNaked
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiasymbol:: Get_isnaked](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-isnaked)。  
  
检索一个标志，指定该函数是否具有[裸](http://msdn.microsoft.com/library/69723241-05e1-439b-868e-20a83a16ab6d)属性 （也就是说，该函数具有由编译器添加任何 prolog 或 epilog 代码）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT get_isNaked(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pFlag`  
 [out]返回`TRUE`如果函数具有`naked`属性; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v8.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Naked 函数调用](http://msdn.microsoft.com/library/2a66847a-a43f-4541-a7be-c9f5f29b5fdb)



