---
title: 如果使用旧版 API 更改查看设置 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - changing view settings
ms.assetid: 12c9b300-0894-4124-96a1-764326176d77
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 053981aceeb72f0c02f1426068919f72b6cdce8d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54984725"
---
# <a name="change-view-settings-by-using-the-legacy-api"></a>通过使用传统的 API 更改视图设置
可以通过用户更改设置核心编辑器功能，如自动换行、 选定内容的边距和虚拟空间**选项**对话框。 但是，还有可能要更改这些设置以编程方式。  
  
## <a name="change-settings-by-using-the-legacy-api"></a>通过使用传统的 API 更改设置  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer>接口公开一组文本编辑器属性。 文本视图包含表示文本视图以编程方式更改的设置的组属性 (GUID_EditPropCategory_View_MasterSettings) 的类别。 一旦已以这种方式更改查看设置，它们不能更改在**选项**对话框重置。  
  
 下面是典型的过程中更改的核心编辑器实例的视图设置。  
  
1.  调用`QueryInterface`上 (<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>) 的<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer>接口。  
  
2.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer.GetPropertyCategory%2A>方法，将值指定为 GUID_EditPropCategory_View_MasterSettings`rguidCategory`参数。  
  
     执行此操作将返回一个指向<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyCategoryContainer>接口，其中包含的视图的强制属性集。 永久强制此组中的任何设置。 如果设置不在此组中，则它将遵循中指定的选项**选项**对话框或用户的命令。  
  
3.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A>方法，指定在相应的设置值`idprop`参数。  
  
     例如，若要强制执行自动换行，请调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.SetProperty%2A>并指定 VSEDITPROPID_ViewLangOpt_WordWrap，值`vt`为`idprop`参数。 在此调用中，`vt`是 VT_BOOL 类型的变体和`vt.boolVal`为 VARIANT_TRUE。  
  
## <a name="reset-changed-view-settings"></a>重置更改视图设置  
 若要重置任何已更改的视图的核心编辑器实例设置，请调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A>方法并指定在相应的设置值`idprop`参数。  
  
 例如，若要允许自动换行自由浮动，您将其从删除的属性类别通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextEditorPropertyContainer.RemoveProperty%2A>，并指定值为 VSEDITPROPID_ViewLangOpt_WordWrap`idprop`参数。  
  
 若要立即删除所有已更改的核心编辑器设置，将值指定为 VSEDITPROPID_ViewComposite_AllCodeWindowDefaults，为 vt`idprop`参数。 在此调用中，vt 是 VT_BOOL 类型的变体和 vt.boolVal 为 VARIANT_TRUE。  
  
## <a name="see-also"></a>请参阅  
 [在核心编辑器](../extensibility/inside-the-core-editor.md)   
 [通过使用传统的 API 访问文本视图](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)   
 [“选项”对话框](../ide/reference/options-dialog-box-visual-studio.md)