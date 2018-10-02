---
title: IDebugArrayObject2 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: de10cd047de173440661201f8daaf9a7630612c6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479983"
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugArrayObject2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayobject2)。  
  
> [!IMPORTANT]
>  在 Visual Studio 2015 中，这种方式实现表达式计算器已弃用。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)并[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 表示一个托管的数组对象，并允许的表达式计算器 (EE) 来确定数组的基索引 （下限）。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugArrayObject2 : IDebugArrayObject  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 这一点被通过托管的调试引擎 (DE)。  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|检索给定数组中的维度数的每个索引 （下限） 的基索引。|  
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|确定数组是否具有基本索引 （下限） 定义。|  
  
## <a name="remarks"></a>备注  
 表达式计算器使用此接口来表示分析树中的托管的数组。  
  
## <a name="requirements"></a>要求  
 标头： Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

