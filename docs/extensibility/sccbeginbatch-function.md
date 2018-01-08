---
title: "SccBeginBatch 函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccBeginBatch
helpviewer_keywords: SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d6415953a350321cb13f2705fa2bb182c278faa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch 函数
此函数启动源代码管理操作批处理的序列。 [SccEndBatch](../extensibility/sccendbatch-function.md)将调用以结束批处理。 这些批不能嵌套。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 此函数的源代码控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|批操作已成功开始。|  
|SCC_E_UNKNOWNERROR|非特定的失败。|  
  
## <a name="remarks"></a>备注  
 源控件批处理用于跨多个项目或多个上下文中执行同样的操作。 批处理可以用于在批处理操作期间消除冗余的每个项目对话框中，从用户体验。 `SccBeginBatch`函数和[SccEndBatch](../extensibility/sccendbatch-function.md)作为函数对用来指示的开头和结尾的运算。 它们不能嵌套。 `SccBeginBatch`设置一个标志，指示批处理操作正在进行。  
  
 批处理操作生效时，源代码管理插件应呈现给用户的最多为任何问题的一个对话框中，并应用所有后续操作从该对话框中的响应。  
  
## <a name="see-also"></a>请参阅  
 [源控件插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)