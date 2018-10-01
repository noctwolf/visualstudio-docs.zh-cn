---
title: SccGetUserOption 函数 |Microsoft Docs
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
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 567dbf987887d203a811a1dc965ecd4a472d5641
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481239"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SccGetUserOption 函数](https://docs.microsoft.com/visualstudio/extensibility/sccgetuseroption-function)。  
  
此函数检索各种特定于用户的选项。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件上下文指针。  
  
 nOption  
 [in]若要检索 （有关可能的选项，请参阅备注） 的选项。  
  
 lpVal  
 [out]与选项相关联的值。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|已成功检索选项。|  
|SCC_E_OPNOTSUPPORTED|不支持选项。|  
|SCC_E_NONSPECIFICERROR|发生了未指定的错误。|  
  
## <a name="remarks"></a>备注  
 此命令支持以下选项：  
  
|用户选项|描述|  
|-----------------|-----------------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|确定用户是否想要签出本地版本的文件。 `lpVal` 分配`SCC_USEROPT_COLV_YES`（用户想要签出本地文件） 或`SCC_USEROPT_COLV_NO`。|  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [错误代码](../extensibility/error-codes.md)

