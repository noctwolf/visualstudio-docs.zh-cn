---
title: CvInitProvider 函数 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
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
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a41e7fe1a6da619e926301b0e1a9b99803fc6d67
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51798296"
---
# <a name="cvinitprovider-function"></a>CvInitProvider 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

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



