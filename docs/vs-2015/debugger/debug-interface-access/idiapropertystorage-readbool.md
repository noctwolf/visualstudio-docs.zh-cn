---
title: IDiaPropertyStorage::ReadBOOL |Microsoft Docs
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
- IDiaPropertyStorage::ReadBOOL
ms.assetid: ad1822db-4572-48f7-9919-f8137f6701f2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a518bf3fd92ed8cc353c77cc9c62a98f2fd0d62
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470148"
---
# <a name="idiapropertystoragereadbool"></a>IDiaPropertyStorage::ReadBOOL
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaPropertyStorage::ReadBOOL](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readbool)。  
  
读取`BOOL`属性组中的值。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT ReadBOOL (   
   PROPID id,  
   BOOL*  pValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [in]要读取的属性的标识符 (`PROPID`定义为 WTypes.h 中`ULONG`)。  
  
 `pValue`  
 [out]返回属性值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`E_INVALIDARG`如果该属性的类型不是`BOOL`。  
  
## <a name="remarks"></a>备注  
 一致的结果，将解释`BOOL`值，以便非零值都`TRUE`零值为`FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



