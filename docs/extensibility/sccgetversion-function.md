---
title: SccGetVersion 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 70beb89f13d2f752f3adb0f25e2b370fa272171a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sccgetversion-function"></a>SccGetVersion 函数
此函数获取受源代码管理插件的源控件插件 api 的版本号。  
  
## <a name="syntax"></a>语法  
  
```cpp  
LONG SccGetVersion(void);  
```  
  
#### <a name="parameters"></a>参数  
 无。  
  
## <a name="return-value"></a>返回值  
 A`LONG`数据类型，包含受支持的源控制插件 API 的版本号：  
  
|WORD|描述|  
|----------|-----------------|  
|HIWORD|主要版本|  
|LOWORD|次要版本|  
  
## <a name="remarks"></a>备注  
 例如，如果源代码管理插件支持版本 1.3 的源控制插件 API，此函数将返回 0x0103。  
  
## <a name="see-also"></a>另请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)