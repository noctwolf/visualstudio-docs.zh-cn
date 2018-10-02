---
title: IDebugAlias2 |Microsoft Docs
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
- IDebugAlias2 interface
ms.assetid: 5252dcbb-8bfe-4d8a-a8e5-b022b194df19
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24f9bf95850dbf374f4069c52e8fba6c2552abf8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469852"
---
# <a name="idebugalias2"></a>IDebugAlias2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugAlias2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugalias2)。  
  
> [!IMPORTANT]
>  在 Visual Studio 2015 中，这种方式实现表达式计算器已弃用。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)并[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 表示的数值别名的变量，并可将表达式计算器 (EE) 来获取该别名的应用程序域。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugAlias2 : IDebugAlias  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 托管的调试引擎 (DE) 实现此接口。  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)接口，此接口实现了以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetAppDomainId](../../../extensibility/debugger/reference/idebugalias2-getappdomainid.md)|检索应用程序域标识符。|  
  
## <a name="remarks"></a>备注  
 别名是以字符串形式的 # 字符，例如 1001 # 后跟一个十进制数。  
  
## <a name="requirements"></a>要求  
 标头： Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

