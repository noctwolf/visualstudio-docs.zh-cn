---
title: 'Idiaaddressmap:: Put_addressmapenabled |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_addressMapEnabled method
ms.assetid: 0f205337-4e59-4383-8059-7b1d207d6dcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f139e6d034fc3b738e345f385fbb8e8ad2150da4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49915381"
---
# <a name="idiaaddressmapputaddressmapenabled"></a>IDiaAddressMap::put_addressMapEnabled
指定是否应使用映射地址将符号地址转换。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT put_addressMapEnabled (   
   BOOL NewVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 NewVal  
 [in]设置为`TRUE`若要启用的符号，翻译或`FALSE`禁用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 可执行文件后处理器有时会更新可执行文件。 DIA 包含一种机制，以支持新布局的符号的转换。  
  
 加载 PDB 文件时，可存储在文件中的地址映射。 但是，有时，当客户端应用程序可能需要提供自己的地址映射通过调用[idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)方法。 如果`set_addressMap`方法成功，客户端应用程序必须调用`put_addressMapEnabled`方法替换`NewVal`参数的`TRUE`来启用该映射的地址。  
  
 可以通过调用检索正在启用地址映射的当前状态[idiaaddressmap:: Get_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)   
 [IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)