---
title: IDebugIDECallback |Microsoft Docs
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
- IDebugIDECallback interface
ms.assetid: 8d31adc0-1c44-4658-8d4f-f4b73e35f4a6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ec4e3fee021b02c80b47635d4872ec1bf51e0cc9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468750"
---
# <a name="idebugidecallback"></a>IDebugIDECallback
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugIDECallback](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugidecallback)。  
  
> [!IMPORTANT]
>  在 Visual Studio 2015 中，这种方式实现表达式计算器已弃用。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)并[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 启用要在调试器的输出窗口中显示一条消息的表达式计算器 (EE)。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugIDECallback : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 托管的调试引擎实现此回调。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 它可供的表达式计算器将输出发送到调试器的输出窗口。  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[DisplayMessage](../../../extensibility/debugger/reference/idebugidecallback-displaymessage.md)|将指定的消息字符串发送到调试器的输出窗口。|  
  
## <a name="requirements"></a>要求  
 标头： Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

