---
title: SccEndBatch 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ec549b5bb0a6c48946edf59f0ab1423cea0ac704
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138218"
---
# <a name="sccendbatch-function"></a>SccEndBatch 函数
此函数最后一批的源代码管理操作。 这些批不能嵌套。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 此函数的源代码控制插件实现应返回以下值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|批操作成功的结论。|  
|SCC_E_UNKNOWNERROR|非特定的失败。|  
  
## <a name="remarks"></a>备注  
 源控件批处理用于跨多个项目或多个上下文中执行相同的源代码管理操作。 批处理可以用于在批处理操作期间消除冗余的对话框中，从用户体验。 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)和`SccEndBatch`函数用作一对，以指示的开头和结尾的运算。 它们不能嵌套。  
  
## <a name="see-also"></a>另请参阅  
 [源控件插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)