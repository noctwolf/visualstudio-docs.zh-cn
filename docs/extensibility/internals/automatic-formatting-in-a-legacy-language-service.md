---
title: 在旧语言服务中自动设置格式 |Microsoft 文档
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
ms.openlocfilehash: e052c62afcf9551cc54373da15071fb3903fe950
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126695"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>自动格式设置在旧语言服务
使用自动格式设置语言服务会自动插入代码段时用户开始键入已知的代码构造。  
  
## <a name="automatic-formatting-behavior"></a>自动格式设置行为  
 例如，键入`if`、 语言服务会自动插入匹配的大括号，或按 ENTER 键时，如果语言服务强制插入点置于新行到适当的缩进级别，具体取决于是否前面行可打开新的作用域。  
  
 有关语言服务的其余部分使用的命令筛选器还可以用于自动格式设置。 此外可以突出匹配的大括号显示通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>。  
  
## <a name="see-also"></a>另请参阅  
 [开发旧版语言服务](../../extensibility/internals/developing-a-legacy-language-service.md)