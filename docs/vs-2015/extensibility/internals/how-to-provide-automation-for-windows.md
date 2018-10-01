---
title: 如何： 提供适用于 Windows 的自动化 |Microsoft Docs
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
- automation [Visual Studio SDK], tool windows
- tool windows, automation
ms.assetid: 512ab2a4-7987-4912-8f40-8804bf66f829
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f6fad49e2841186cea677a165bdb48c4a1af5b41
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478739"
---
# <a name="how-to-provide-automation-for-windows"></a>如何： 提供适用于 Windows 的自动化
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 为 Windows 提供自动化](https://docs.microsoft.com/visualstudio/extensibility/internals/how-to-provide-automation-for-windows)。  
  
你可以提供文档和工具窗口的自动化。 提供自动化是建议您无论何时你想要使自动化对象在一个窗口，并在环境已不提供现成的自动化对象，方式与在任务列表。  
  
## <a name="automation-for-tool-windows"></a>自动化工具 Windows  
 通过返回一个标准工具窗口上环境提供自动化<xref:EnvDTE.Window>对象下面的过程中所述：  
  
#### <a name="to-provide-automation-for-tool-windows"></a>若要提供自动化的工具窗口  
  
1.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A>方法通过使用环境<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>作为`VSFPROPID`参数，以获取`Window`对象。  
  
2.  当调用方请求特定于 VSPackage 的自动化对象通过工具窗口<xref:EnvDTE.Window.Object%2A>，环境调用`QueryInterface`有关`IExtensibleObject`， <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>，或`IDispatch`接口。 这两`IExtensibleObject`并`IVsExtensibleObject`提供<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject.GetAutomationObject%2A>方法。  
  
3.  当环境然后调用`GetAutomationObject`方法并传递`NULL`，表示通过响应返回特定于 VSPackage 的对象。  
  
4.  如果调用`QueryInterface`有关`IExtensibleObject`并`IVsExtensibleObject`失败，则环境在调用`QueryInterface`为`IDispatch`。  
  
## <a name="automation-for-document-windows"></a>自动化文档 Windows  
 一种标准<xref:EnvDTE.Document>对象也是可从环境中，虽然编辑器可以有自己的实现`T:EnvDTE.Document`通过实现对象`IExtensibleObject`接口和响应的`GetAutomationObject`。  
  
 此外，编辑器可以提供特定于 VSPackage 的自动化对象，通过检索<xref:EnvDTE.Document.Object%2A>方法，通过实现`IVsExtensibleObject`或`IExtensibleObject`接口。 [VSSDK 示例](../../misc/vssdk-samples.md)有助于 RTF 特定于文档的自动化对象。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibleObject>

