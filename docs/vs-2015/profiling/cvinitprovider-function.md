---
title: CvInitProvider 函数 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvInitProvider
helpviewer_keywords:
- CvInitProvider method
ms.assetid: ba1863ad-e35f-4d34-a2f2-5e68957d1915
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a65df9e9ccc61aec0a96f5f467962d46eb88b78c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478994"
---
# <a name="cvinitprovider-function"></a>CvInitProvider 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CvInitProvider 函数](https://docs.microsoft.com/visualstudio/profiling/cvinitprovider-function)。  
  
初始化标记提供程序。 必须在任何其他并发可视化工具 SDK 函数之前调用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CvInitProvider(  
   _In_ const GUID* pGuid,  
   _Out_ PCV_PROVIDER* ppProvider  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pGuid`  
 提供程序 GUID。 不能为 NULL。  
  
 `ppProvider`  
 输出变量的地址，用于存储提供程序上下文。 不能为 NULL。  
  
## <a name="return-value"></a>返回值  
 成功初始化提供程序时返回 S_OK，出现任何错误时返回错误代码。 使用 SUCCEEDED/FAILED 宏检查错误条件。  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkers.h  
  
## <a name="see-also"></a>请参阅  
 [C++ 库参考](../profiling/cpp-library-reference.md)



