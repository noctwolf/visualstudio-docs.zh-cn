---
title: IDebugCustomAttributeQuery |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ea9c37dbb889a622d0b428d53144c27d0c04aef9
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706452"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
表示对方法或类型的自定义属性的查询。

## <a name="syntax"></a>语法

```
IDebugCustomAttributeQuery : IUnknown
```

## <a name="methods"></a>方法
 此接口实现以下方法：

|方法|描述|
|------------|-----------------|
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|检索在给定其名称的自定义属性。|
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|确定指定中定义自定义属性。|

## <a name="requirements"></a>要求
 标头：Sh.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll