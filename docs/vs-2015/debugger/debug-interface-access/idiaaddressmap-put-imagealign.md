---
title: 'Idiaaddressmap:: Put_imagealign |Microsoft Docs'
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
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6743d2a39f2326b167da746fbb2da928c0b75aaf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471766"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaaddressmap:: Put_imagealign](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-put-imagealign)。  
  
设置的图像对齐方式。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 NewVal  
 [in]新的图像对齐方式可执行文件有值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 指定的内存边界对齐图像 （加载可执行文件）。 由当前的系统体系结构以及编译和链接时间选项，可能会影响此对齐方式。 图像对齐方式是始终在字节边界上。 下面的图像对齐方式列出有效值： 1、 2、 4、 8、 16、 32 和 64 字节边界。  
  
 可以通过调用检索当前的图像对齐方式[idiaaddressmap:: Get_imagealign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)方法。  
  
> [!NOTE]
>  可以调用此方法时已加载图像。 `put_imageAlign`图像已被移动或更改和新的对齐方式是所需时通常使用方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)



