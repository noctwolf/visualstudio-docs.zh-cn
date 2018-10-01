---
title: 'Idialinenumber:: Get_relativevirtualaddress |Microsoft Docs'
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
- IDiaLineNumber::get_relativeVirtualAddress method
ms.assetid: ba8142e3-5c77-43cc-bd33-c077dcc18cab
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2b1e5e38cca5c96c53a9eeb34e3e1aad6aa312f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470481"
---
# <a name="idialinenumbergetrelativevirtualaddress"></a>IDiaLineNumber::get_relativeVirtualAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idialinenumber:: Get_relativevirtualaddress](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialinenumber-get-relativevirtualaddress)。  
  
检索块的相对虚拟地址 (RVA)。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_relativeVirtualAddress (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回在块的图像的相对虚拟地址。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



