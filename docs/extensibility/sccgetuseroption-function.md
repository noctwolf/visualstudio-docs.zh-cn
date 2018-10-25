---
title: SccGetUserOption 函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b906dc9585ed51640ca36f366fe6a1b0d3a03aa2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49928199"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption 函数
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