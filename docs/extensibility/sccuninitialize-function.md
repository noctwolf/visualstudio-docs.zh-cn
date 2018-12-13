---
title: SccUninitialize 函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: e9d992428dd6358cee2b6a46efc0816e7840c449
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49948026"
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
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|清理已成功完成。|  
  
## <a name="remarks"></a>备注  
 源代码管理插件负责准备关闭并释放该插件为上下文结构已分配的内存。 为每个插件的给定实例一次调用的函数。 调用[SccInitialize](../extensibility/sccinitialize-function.md)位于此调用。 没有项目仍可以在调用时打开`SccUninitialize`。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)