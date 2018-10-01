---
title: SccGetExtendedCapabilities 函数 |Microsoft Docs
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
- SccGetExtendedCapabilities
helpviewer_keywords:
- SccGetExtendedCapabilities function
ms.assetid: 588c6a92-2147-4d8b-a357-96ca7da0a092
caps.latest.revision: 17
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 016b44e8dcd8218b8c3fbd569ba6a27b77d9d204
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479861"
---
# <a name="sccgetextendedcapabilities-function"></a>SccGetExtendedCapabilities 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SccGetExtendedCapabilities 函数](https://docs.microsoft.com/visualstudio/extensibility/sccgetextendedcapabilities-function)。  
  
此函数返回受源代码管理插件的其他功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccGetExtendedCapabilities(  
   LPVOID pContext,  
   LONG lSccExCaps,  
   LPBOOL pbSupported  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件上下文指针。  
  
 lSccExCaps  
 [in]标志，指定对其进行测试的扩展的功能 (请参阅中的扩展功能代码表[功能标志](../extensibility/capability-flags.md)可能标志)。  
  
 pbSupported  
 [out]返回非零值 (`TRUE`) 如果支持指定的功能; 否则，返回零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|获取功能操作已成功完成。|  
|SCC_E_UNKNOWNERROR<br /><br /> SCC_E_NONSPECIFICERROR|出现未知或未指定错误。|  
  
## <a name="remarks"></a>备注  
 按需; 调用此方法也就是说，当一项功能需要进行测试，调用此方法是可确定是否支持功能。 指定一次只有一个标志。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [错误代码](../extensibility/error-codes.md)   
 [功能标志](../extensibility/capability-flags.md)

