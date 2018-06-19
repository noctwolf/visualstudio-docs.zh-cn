---
title: 'Idiasymbol:: Get_addressoffset |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_addressOffset method
ms.assetid: c15639b0-7f37-46c7-891b-40273b7f6319
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d00838fc3f76221293241656743bbf5a2a7f4d26
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466352"
---
# <a name="idiasymbolgetaddressoffset"></a>IDiaSymbol::get_addressOffset
检索地址位置的偏移量的部分。 何时使用[LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)设置为`LocIsStatic`。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回地址位置的偏移量的部分。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 对于位于外部的 DLL 的静态成员，此方法返回的偏移量可能为 0，此方法依赖于获取的成员的虚拟地址。 虚拟地址都有效才[idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)中的方法[IDiaSession](../../debugger/debug-interface-access/idiasession.md)接口已调用具有非零参数指定的 DLL 的加载地址。  
  
 若要获取地址的部分部分，调用[idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)方法。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v7.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)   
 [Idiasymbol:: Get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)   
 [Idiasession:: Put_loadaddress](../../debugger/debug-interface-access/idiasession-put-loadaddress.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)