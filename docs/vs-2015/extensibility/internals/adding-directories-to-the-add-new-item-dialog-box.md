---
title: 将目录添加到添加新建项对话框 |Microsoft Docs
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
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9a4623df5794ae29b97bbbdc077c465d822d6f4d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471043"
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>将目录添加到“添加新项”对话框
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[添加到添加新项对话框中的目录](https://docs.microsoft.com/visualstudio/extensibility/internals/adding-directories-to-the-add-new-item-dialog-box)。  
  
下面的代码示例演示如何注册一组新的目录**添加新项**对话框。 目录**添加新项**对话框是不同的每个项目。 因此，在中找到的项目子项下注册目录\<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>注册表脚本  
  
```  
NoRemove Projects  
{  
  NoRemove %GUID_Project%  
  {  
    NoRemove AddItemTemplates  
    {  
      NoRemove TemplateDirs  
      {  
        ForceRemove %CLSID_Package%  
        {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
          {  
            val TemplatesDir = s '%Template_Path%'     
            val SortPriority = d 2000  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
 Template_Path 值指定包含的项目模板的目录的完整路径。 这些模板可以是.vsz 文件或要克隆的原型的模板文件。  
  
 SortPriority 值指定排序优先级。  
  
## <a name="adding-items-to-an-existing-project"></a>将项添加到现有项目  
 此外可以向现有项目添加项。 例如，对于[!INCLUDE[csprcs](../../includes/csprcs-md.md)]项目中，您可以将项添加到\<根 > \Program Files\Microsoft Visual Studio \VC#\CSharpProjectItems\LocalProjectItems 文件夹。 在这种情况下`%GUID_Project%`是 C# 项目 ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}) 的 GUID。  
  
 此外可以通过编程项目子类型来扩展现有的项目。 项目子类型，而无需编写新的项目类型可以扩展项目。 有关项目子类型的详细信息，请参阅[项目子类型](../../extensibility/internals/project-subtypes.md)。  
  
## <a name="see-also"></a>请参阅  
 [注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)   
 [将项添加到添加新项对话框](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [将目录添加到“新建项目”对话框](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)

