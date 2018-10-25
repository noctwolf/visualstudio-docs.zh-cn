---
title: SccIsMultiCheckoutEnabled 函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccIsMultiCheckoutEnabled
helpviewer_keywords:
- SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 642f42de508702bfd1dd344b489ec875de9deedc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49845766"
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此函数检查源代码管理插件是否允许多次签出文件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控制插件上下文结构。  
  
 pbMultiCheckout  
 [out]指定是否为此项目 （非零值表示，支持多个签出） 启用多个签出。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|检查成功。|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|非特定故障。|  
  
## <a name="remarks"></a>备注  
 IDE 将使两个检查，以确定是否文件可以签出同时由多个用户。 首先，源代码管理系统必须支持多个签出。 源代码管理插件可以指定此功能在初始化期间通过指定`SCC_CAP_MULTICHECKOUT`。 此后，作为第二个检查中，IDE 会调用此函数可确定当前的项目支持多个签出。 如果所选项目支持多个签出，该插件返回一个成功的代码，并设置`pbMultiCheckout`不为零 (`TRUE`) 或`FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)

