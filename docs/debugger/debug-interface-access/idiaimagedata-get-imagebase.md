---
title: 'Idiaimagedata:: Get_imagebase |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6e0037ef4bbbfc499d23e517e0fb3522b8f042c7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822969"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
检索其中应基于映像的内存位置。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回建议的图像的基值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 由于映像基冲突而进行映像可能会重新设定基址自动到未使用的内存位置在加载时。 此方法返回已在编译时存储在模块中的基本提示 （建议的内存位置）。  
  
## <a name="see-also"></a>请参阅  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)