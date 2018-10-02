---
title: IDiaPropertyStorage::ReadPropertyNames |Microsoft Docs
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
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e7f20674da015cb31747afc9cce413d3f2290b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469129"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaPropertyStorage::ReadPropertyNames](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readpropertynames)。  
  
检索对应的字符串名称给定属性标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cpropid`  
 [in]中的属性 id 数`rgpropid`。  
  
 `rgpropid`  
 [in]要为其获取名称的属性 id 的数组 (`PROPID`定义为 WTypes.h 中`ULONG`)。  
  
 `rglpwstrName`  
 [in、 out]指定的属性 id 的属性名称的数组。 数组必须是预分配用于保存请求的数目的属性名称，并且必须能够至少容纳`cpropid``BSTR`字符串。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 返回的属性名称，必须释放 (通过调用`SysFreeString`函数) 在不再需要时。  
  
## <a name="see-also"></a>请参阅  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



