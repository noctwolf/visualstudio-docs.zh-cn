---
title: IDebugPrimitiveTypeField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPrimitiveTypeField interface
ms.assetid: 73a428fd-797e-4ceb-8392-ba16f1c5226b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 25af7b2126be79901ceb97d6c93786d59111bfe1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703508"
---
# <a name="idebugprimitivetypefield"></a>IDebugPrimitiveTypeField
表示基元类型枚举值从[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。

## <a name="syntax"></a>语法

```
IDebugPrimitiveTypeField : IDebugField
```

## <a name="methods"></a>方法
 除了上的方法[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口，此接口实现了以下方法：

|方法|描述|
|------------|-----------------|
|[GetPrimitiveType](../../../extensibility/debugger/reference/idebugprimitivetypefield-getprimitivetype.md)|检索与此字段关联的基元类型。|

## <a name="requirements"></a>要求
 标头：Sh.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll