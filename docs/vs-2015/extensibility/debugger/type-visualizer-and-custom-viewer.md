---
title: 键入可视化工具和自定义查看器 |Microsoft Docs
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
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d347e7b18722aa8f8901abac3966150b3dca97cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471242"
---
# <a name="type-visualizer-and-custom-viewer"></a>类型可视化工具和自定义查看器
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[类型可视化工具和自定义查看器](https://docs.microsoft.com/visualstudio/extensibility/debugger/type-visualizer-and-custom-viewer)。  
  
类型可视化工具是非常特定的格式显示一段数据的组件。 此格式是完全取决于该可视化工具的实施者，无论是最终用户或第三方供应商的可视化工具。  
  
 自定义查看器是非常特定的格式显示一段数据自定义表达式计算器的一部分。 此格式是完全取决于自定义查看器中，这意味着格式是由表达式计算器 (EE) 实现的实施者。  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>表达式计算器中的类型可视化工具的支持  
 EE 可以通过支持一套可视化工具可以访问接口支持类型可视化工具： 接口如[IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)并[IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)。 但请注意，EE 概不负责实现类型可视化工具本身： EE 只允许外部可视化工具对其类型信息的访问。 此类可视化工具可能会随 EE 并安装在由其他第三方供应商或甚至最终用户提供的 Visual Studio 中的适当位置。  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>表达式计算器中的自定义查看器的支持  
 EE 还可以支持自定义查看器在其中 EE 本身提供了用于查看数据类型的代码。 自定义查看器实现[IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)所需接口，处理的任何格式显示数据的所有任务; 查看器可以完全控制如何显示，并且甚至还可以允许要修改的数据。 在产品发布时提供 EE 的任何自定义查看器随附 EE。  
  
## <a name="see-also"></a>请参阅  
 [调试器组件](../../extensibility/debugger/debugger-components.md)   
 [表达式计算器](../../extensibility/debugger/expression-evaluator.md)   
 [调试引擎](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)

