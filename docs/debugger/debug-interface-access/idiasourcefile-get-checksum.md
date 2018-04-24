---
title: 'Idiasourcefile:: Get_checksum |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 002ad16d94467c135e08ef0040fd7ffd51462719
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
检索的校验和字节。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbData`  
 [in]数据缓冲区，以字节为单位的大小。  
  
 `pcbData`  
 [out]返回校验和字节的数。 此参数不能为`NULL`。  
  
 `data`  
 [在中，out]使用校验和字节填充缓冲区。 如果此参数为`NULL`，然后`pcbData`返回所需的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 若要确定用于生成校验和字节的校验和算法的类型，请调用[idiasourcefile:: Get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)方法。  
  
 从源代码文件的映像通常生成校验和，因此，在源文件中的更改会反映在校验和字节中的更改。 如果不匹配的校验和字节校验和从文件中，已加载映像生成，则该文件应被视为已损坏或篡改。  
  
 典型的校验和永远不会超过 32 个字节的大小，但不是会假定这是校验和的最大大小。 设置`data`参数`NULL`若要获取的检索校验和所需的字节数。 然后分配适当的大小的缓冲区，并调用此方法一次使用新的缓冲区。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)