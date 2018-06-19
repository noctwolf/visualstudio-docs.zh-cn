---
title: 'Idiasectioncontrib:: Get_nopad |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_nopad method
ms.assetid: f5c08603-0b3e-4e81-acf1-1b95a6a83bed
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b26005e6e7062fcf5a3a6f0a9aba4ac7a79b92f7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31461010"
---
# <a name="idiasectioncontribgetnopad"></a>IDiaSectionContrib::get_nopad
检索一个标志，指示是否部分应不填充到下一步的内存边界。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_nopad(  
   BOOL* pRetVal  
};  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果部分应不填充到下一步的内存边界; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果不支持此属性。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 这是通常仅在较旧的文件上会出现一个属性。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)