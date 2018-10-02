---
title: SccGetVersion 函数 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2b5c5e5e6035d6ce0b81ba747efa3cea65ab2f97
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482654"
---
# <a name="sccgetversion-function"></a>SccGetVersion 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SccGetVersion 函数](https://docs.microsoft.com/visualstudio/extensibility/sccgetversion-function)。  
  
此函数获取源代码管理插件支持的源控制插件 API 的版本号。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 一个`LONG`包含版本号的受支持的源控制插件 API 的数据类型：  
  
|WORD|描述|  
|----------|-----------------|  
|HIWORD|主要版本|  
|使用 LOWORD|次要版本|  
  
## <a name="remarks"></a>备注  
 例如，如果源代码管理插件支持的源控制插件 API 版本 1.3，此函数将返回 0x0103。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)

