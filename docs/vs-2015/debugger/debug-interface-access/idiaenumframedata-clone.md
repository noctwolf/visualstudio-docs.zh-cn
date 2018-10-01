---
title: 'Idiaenumframedata:: Clone |Microsoft Docs'
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
- IDiaEnumFrameData::Clone Method
ms.assetid: 28a17300-1626-422f-a17a-3a4d3872c37c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9b658e0cf6d2d92df19d57051611e0ebb86663a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468631"
---
# <a name="idiaenumframedataclone"></a>IDiaEnumFrameData::Clone
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumframedata:: Clone](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumframedata-clone)。  
  
创建一个包含当前枚举数形式的相同枚举状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Clone(   
   IDiaEnumFrameData** ppenum  
);  
```  
  
#### <a name="parameters"></a>参数  
 ppenum  
 [out]返回[IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)对象，其中包含重复的枚举器。 重复的数据不是的框架，仅枚举器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)



