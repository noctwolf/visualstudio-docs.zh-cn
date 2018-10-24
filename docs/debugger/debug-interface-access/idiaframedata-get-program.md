---
title: 'Idiaframedata:: Get_program |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 125c809f32b34b077fae0bb661ef9c2f010a4b8b
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49849458"
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
检索用于计算的寄存器集之前调用当前函数的程序字符串。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回程序字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 程序字符串是为了建立序言解释宏的序列。 例如，典型的堆栈帧可能使用的计划字符串`"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`。 格式为反向波兰语表示法，其中运算符遵循操作数。 `T0` 表示在堆栈上的临时变量。 此示例将执行以下步骤：  
  
1. 将寄存器的内容移`ebp`到`T0`。  
  
2. 添加`4`中的值`T0`若要生成一个地址、 从该地址获取值并将值存储在寄存器中`eip`。  
  
3. 从存储中的地址获取该值`T0`并将该值存储在寄存器中`ebp`。  
  
4. 添加`8`中的值`T0`并将该值存储在寄存器中`esp`。  
  
   请注意程序字符串是特定于 CPU 设置为表示由当前堆栈帧的函数的调用约定。  
  
## <a name="see-also"></a>请参阅  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)