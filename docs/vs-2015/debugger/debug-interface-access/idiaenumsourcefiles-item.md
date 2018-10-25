---
title: 'Idiaenumsourcefiles:: Item |Microsoft Docs'
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
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3766f2a9bb362587584583d5eb767540e75e7294
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49901523"
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

通过索引检索源文件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)要检索对象。 索引是 0 到范围内`count`-1，其中`count`返回的[idiaenumsourcefiles:: Get_count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)方法。  
  
 sourceFile  
 [out]返回[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)对象，表示所需的源文件。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)



