---
title: 旧版语言服务中的自动格式设置 |Microsoft Docs
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
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 46e5f30d01a3063a3683aa3cae4ae1da3e0aa141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480660"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>在旧版语言服务中进行自动格式设置
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[旧版语言服务中的自动格式设置](https://docs.microsoft.com/visualstudio/extensibility/internals/automatic-formatting-in-a-legacy-language-service)。  
  
使用自动设置格式语言服务会自动插入代码片段时在用户开始键入已知的代码构造。  
  
## <a name="automatic-formatting-behavior"></a>自动格式设置行为  
 例如，键入`if`、 语言服务将自动插入匹配大括号，或按 ENTER 键时，如果语言服务将强制插入点置于新行到适当的缩进级别，具体取决于是否在前面行可打开新的作用域。  
  
 命令筛选器的语言服务的其余部分使用，还可用于自动格式设置。 此外可以突出显示匹配大括号显示通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>。  
  
## <a name="see-also"></a>请参阅  
 [开发旧版语言服务](../../extensibility/internals/developing-a-legacy-language-service.md)

