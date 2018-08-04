---
title: 旧版语言服务中的自动格式设置 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56910a984fabb3ac4825fd438be17745126692a6
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39500665"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>自动格式设置在旧版语言服务
使用自动设置格式语言服务会自动插入代码片段时在用户开始键入已知的代码构造。  
  
## <a name="automatic-formatting-behavior"></a>自动格式设置行为  
 例如，键入*如果*、 语言服务将自动插入匹配大括号，或按 ENTER 键时，如果语言服务将强制插入点置于新行到适当的缩进级别，具体取决于是否在前面的行可打开新的作用域。  
  
 命令筛选器的语言服务的其余部分使用，还可用于自动格式设置。 此外可以突出显示匹配大括号显示通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>。  
  
## <a name="see-also"></a>请参阅  
 [开发旧版语言服务](../../extensibility/internals/developing-a-legacy-language-service.md)