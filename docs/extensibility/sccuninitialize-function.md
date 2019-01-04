---
title: SccUninitialize 函数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64e894fe2ce1eaf6f74ed01d2e76f7ce3d33f9fb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949636"
---
# <a name="sccuninitialize-function"></a>SccUninitialize 函数
此函数将清除任何分配或由以前调用创建的打开连接[SccInitialize](../extensibility/sccinitialize-function.md)以准备关闭源代码管理插件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>参数  
 pvContext  
 [in]在中创建指向源控制插件上下文结构的指针[SccInitialize](../extensibility/sccinitialize-function.md)。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|清理已成功完成。|  
  
## <a name="remarks"></a>备注  
 源代码管理插件负责准备关闭并释放该插件为上下文结构已分配的内存。 为每个插件的给定实例一次调用的函数。 调用[SccInitialize](../extensibility/sccinitialize-function.md)位于此调用。 没有项目仍可以在调用时打开`SccUninitialize`。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)