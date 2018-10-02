---
title: SccEndBatch 函数 |Microsoft Docs
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
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 075e661976062d2de985fa52110ea87840c2ab21
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470836"
---
# <a name="sccendbatch-function"></a>SccEndBatch 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SccEndBatch 函数](https://docs.microsoft.com/visualstudio/extensibility/sccendbatch-function)。  
  
此函数最后一批的源代码管理操作。 这些批不能嵌套。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|一批操作已成功结束。|  
|SCC_E_UNKNOWNERROR|非特定故障。|  
  
## <a name="remarks"></a>备注  
 使用源控制批处理跨多个项目或多个上下文中执行相同的源代码管理操作。 若要在批处理操作期间消除冗余的对话框中，从用户体验，可以使用批处理。 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)和`SccEndBatch`函数用作一个对，以指示的开头和结尾的操作。 它们不能嵌套。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)

