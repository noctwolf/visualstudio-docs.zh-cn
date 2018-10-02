---
title: 杂项文件项目 |Microsoft Docs
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
- files, adding existing files to solutions
- Miscellaneous Files project
- Solution Items folder
- files, opening with Miscellaneous Files project
ms.assetid: 93a278a8-d4f4-400b-8945-4f1b0a2b5bac
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bdcbe1901deb472969c993b826660d03d12b2cf3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476696"
---
# <a name="miscellaneous-files-project"></a>杂项文件项目
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[杂项文件项目](https://docs.microsoft.com/visualstudio/extensibility/internals/miscellaneous-files-project)。  
  
当用户打开项目项时，IDE 将分配给杂项文件项目不是解决方案中的任何项目的成员的任何项目。  
  
 项目扮演重要角色确定当用户打开项目项时，将使用的编辑器。 可以设计一个项目以使用特定于项目的编辑器或标准编辑器打开某些文件。  
  
 特定于项目的编辑器通常要求用户具有特殊知识，或者使用从项目的特殊接口。 有关详细信息，请参阅[如何： 打开项目特定的编辑器](../../extensibility/how-to-open-project-specific-editors.md)。  
  
 标准编辑器可以打开任何项目中的特定扩展的任何文件。 用户可以自定义某些标准编辑器中，如[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]文本编辑器中的，对于项目，但仍保留了其公共的字符。 通过使用创建标准编辑器<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>方法。  
  
 如果解决方案中的没有项目响应，它可以打开项目项，则 IDE 提供了一个名为杂项文件项目打开任何文件的特殊项目。  
  
 此特殊项目提供了用于打开项目的上下文之外的文件。 处理过程中的<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A>杂项文件项目的方法，始终响应以非常低的优先级。 因此，杂项文件项目始终依赖任何优先级较高的项目都可以打开文件。  
  
 杂项文件项目不需要用户显式创建其与**新的项目**对话框。 此外，杂项文件项目不永久管理项目成员的列表。 它使用一项可选功能来记录每个用户最近使用的文件的列表。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY>   
 [如何： 打开项目特定的编辑器](../../extensibility/how-to-open-project-specific-editors.md)   
 [如何： 打开标准编辑器](../../extensibility/how-to-open-standard-editors.md)   
 [添加项目和项目项模板](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [添加项目和项目项模板](../../extensibility/internals/adding-project-and-project-item-templates.md)

