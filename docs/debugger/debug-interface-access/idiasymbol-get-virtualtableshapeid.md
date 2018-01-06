---
title: "Idiasymbol:: Get_virtualtableshapeid |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_virtualTableShapeId method
ms.assetid: cbee9944-817a-4805-9c08-fac8e0da58b7
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6bc142df6d01a9c1ac49f656ec06250f5aba4fdd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetvirtualtableshapeid"></a>IDiaSymbol::get_virtualTableShapeId
检索虚拟表形状符号标识符的符号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_virtualTableShapeId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回的符号的虚拟表形状符号 ID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 标识符是由 DIA SDK，可将标记为唯一的所有符号的唯一值。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)