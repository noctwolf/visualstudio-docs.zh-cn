---
title: "SccGetVersion 函数 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccGetVersion
helpviewer_keywords:
- SccGetVersion function
ms.assetid: a6e786bf-744e-4272-9e21-0be44d23b1a1
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2aef7ed21124c2e3555442819461f1989388ab22
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)