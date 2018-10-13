---
title: 'Idiaaddressmap:: Set_imageheaders |Microsoft Docs'
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
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8ef978dfe6da37c06574fd2ec72e87ba21b214b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294939"
---
# <a name="idiaaddressmapsetimageheaders"></a>IDiaAddressMap::set_imageHeaders
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

设置映像标头，以便相对虚拟地址转换。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT set_imageHeaders (   
   DWORD cbData,  
   BYTE  data[],  
   BOOL  originalHeaders  
);  
```  
  
#### <a name="parameters"></a>参数  
 cbData  
 [in]标头数据的字节数。 必须是`n*sizeof(IMAGE_SECTION_HEADER)`其中`n`是可执行文件中的部分标头数。  
  
 数据]  
 [in]一个数组`IMAGE_SECTION_HEADER`结构，以用作映像标头。  
  
 originalHeaders  
 [in]设置为`FALSE`从新的映像，映像标头是否`TRUE`如果它们反映在升级之前的原始映像。 通常情况下，这将设置为`TRUE`仅在通过调用组合[idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)方法。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 `IMAGE_SECTION_HEADER`结构在 Winnt.h 中声明，表示可执行文件的图像部分标头格式。  
  
 取决于相对虚拟地址计算`IMAGE_SECTION_HEADER`值。 通常情况下，DIA 检索这些程序数据库 (.pdb) 文件中。 如果缺少这些值，DIA 是无法计算相对虚拟地址并[idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)方法将返回`FALSE`。 然后，客户端必须调用[idiaaddressmap:: Put_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)方法，以提供图像本身中的缺少映像标头后使相对虚拟地址计算。  
  
## <a name="see-also"></a>请参阅  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [Idiaaddressmap:: Get_relativevirtualaddressenabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)



