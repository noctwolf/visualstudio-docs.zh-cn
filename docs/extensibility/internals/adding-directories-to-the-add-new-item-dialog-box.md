---
title: 添加到目录添加新项对话框 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b8d9989e8cf4ec8f0eb714a26e73d89fba339b71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127743"
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>添加到目录添加新项对话框
下面的代码示例演示如何注册一组新的目录**添加新项**对话框。 目录**添加新项**对话框中是不同的每个项目。 因此，在中找到的项目子项下注册目录\<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
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
  
 Template_Path 值指定包含的项目模板的目录的完整路径。 .Vsz 文件或原型的模板文件要克隆，可以是这些模板。  
  
 SortPriority 值指定排序的优先级。  
  
## <a name="adding-items-to-an-existing-project"></a>将项添加到现有项目  
 你还可以向现有项目添加项。 例如，对于[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]项目中，你可以将项添加到\<根 > files\microsoft Visual Studio \VC#\CSharpProjectItems\LocalProjectItems 文件夹。 在这种情况下`%GUID_Project%`是 C# 项目 ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}) 的 GUID。  
  
 你还可以通过编程项目子类型来扩展现有项目。 使用项目子类型，可以扩展一个项目，而无需编写新的项目类型。 有关项目子类型的详细信息，请参阅[项目子类型](../../extensibility/internals/project-subtypes.md)。  
  
## <a name="see-also"></a>另请参阅  
 [注册项目和项模板](../../extensibility/internals/registering-project-and-item-templates.md)   
 [将项添加到添加新项对话框](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [将目录添加到“新建项目”对话框](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)