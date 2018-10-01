---
title: 在托管代码中的 HRESULT 信息 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSPackages, HRESULT information
- HRESULT, managed VSPackages
ms.assetid: 0795ee94-17a8-4327-bf57-27cd5e312a4c
caps.latest.revision: 29
manager: douge
ms.openlocfilehash: c87fc618f1c80b60bbd2f95537dc70a83eb2bdc7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469116"
---
# <a name="hresult-information-in-managed-code"></a>在托管代码中的 HRESULT 信息
当遇到 HRESULT 返回值时，托管代码和 COM 之间的交互可能会导致一些问题。  
  
 在 COM 接口中，HRESULT 返回值可以发挥以下作用：  
  
-   提供错误的信息 (例如， <xref:Microsoft.VisualStudio.VSConstants.E_INVALIDARG>)。  
  
-   提供有关正常程序行为的状态信息。  
  
 当 COM 调入托管代码时，HRESULT 可能会导致以下问题：  
  
-   返回小于零的 HRESULT 值（故障代码）的 COM 函数会生成异常。  
  
-   定期返回两个或多个不同成功代码，例如，COM 方法<xref:Microsoft.VisualStudio.VSConstants.S_OK>或<xref:Microsoft.VisualStudio.VSConstants.S_FALSE>，不能为可分辨。  
  
 因为许多[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]COM 函数返回的 HRESULT 值小于零或返回不同的成功代码[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]互操作程序集已写入，以便保留方法签名。 所有[!INCLUDE[vsipsdk](../includes/vsipsdk-md.md)]互操作方法均为`int`类型。 HRESULT 值通过互操作层传递，无需更改且不会生成异常。  
  
 由于 COM 函数向调用它的托管方法返回 HRESULT，因此，进行调用的方法必须检查 HRESULT，并根据需要引发异常。  
  
## <a name="handling-hresults-returned-to-managed-code-from-com"></a>处理从 COM 返回到托管代码的 HRESULT  
 当从托管代码调用 COM 接口时，请检查 HRESULT 值并根据需要引发异常。 <xref:Microsoft.VisualStudio.ErrorHandler>类包含<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>方法，将引发 COM 异常，具体取决于相应的 HRESULT 值传递给它。  
  
 默认情况下，<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>每当它传递的值小于零的 HRESULT 时引发异常。 在此类 Hresult 是可接受的值，其中应引发任何异常的情况下，应将其他 HRESULT 的值传递给<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>测试值之后。 如果所测试的 HRESULT 与显式传递到任何 HRESULT 值匹配<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>，不会引发异常。  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.VSConstants>类通用 hresult 包含常量等<xref:Microsoft.VisualStudio.VSConstants.S_OK>并<xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>，和[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]HRESULT，例如，<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>和<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>。 <xref:Microsoft.VisualStudio.VSConstants> 此外提供了<xref:Microsoft.VisualStudio.ErrorHandler.Succeeded%2A>和<xref:Microsoft.VisualStudio.ErrorHandler.Failed%2A>方法，它们分别对应于 com 的 SUCCEEDED 和 FAILED 宏  
  
 例如，考虑以下函数调用中，<xref:Microsoft.VisualStudio.VSConstants.E_NOTIMPL>是可接受的返回值，但其他 HRESULT 小于零表示错误。  
  
 [!code-csharp[VSSDKHRESULTInformation#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkhresultinformation/cs/vssdkhresultinformationpackage.cs#1)]
 [!code-vb[VSSDKHRESULTInformation#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkhresultinformation/vb/vssdkhresultinformationpackage.vb#1)]  
  
 如果有多个可接受的返回值，只是可以将其他 HRESULT 值追加到在调用列表<xref:Microsoft.VisualStudio.ErrorHandler.ThrowOnFailure%2A>。  
  
 [!code-csharp[VSSDKHRESULTInformation#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkhresultinformation/cs/vssdkhresultinformationpackage.cs#2)]
 [!code-vb[VSSDKHRESULTInformation#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkhresultinformation/vb/vssdkhresultinformationpackage.vb#2)]  
  
## <a name="returning-hresults-to-com-from-managed-code"></a>从托管代码将 HRESULT 返回到 COM  
 如果没有发生异常，托管代码返回<xref:Microsoft.VisualStudio.VSConstants.S_OK>到调用它的 COM 函数。 COM 互操作支持托管代码中强类型化的常见异常。 例如，收到不可接受的方法`null`参数，则会引发<xref:System.ArgumentNullException>。  
  
 如果您不能确定哪个异常引发，但您知道 HRESULT 你想要返回到 COM，可以使用<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>方法会引发相应的异常。 这样即使使用了非标准错误，例如， <xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>。 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 尝试的 HRESULT 映射传递给它对强类型化的异常。 如果无法映射，它会改为引发一般的 COM 异常。 最终结果是相应的 HRESULT 将传递到<xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>从托管代码返回到调用它的 COM 函数。  
  
> [!NOTE]
>  异常会降低性能，它用于指示程序的异常状况。 对于所发生的状况，通常应以内联方式处理，而不是引发异常。  
  
## <a name="see-also"></a>请参阅  
 [托管的 Vspackage](../misc/managed-vspackages.md)   
 [与非托管代码交互操作](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [如何： 映射 Hresult 和异常](http://msdn.microsoft.com/library/610b364b-2761-429d-9c4a-afbc3e66f1b9)   
 [生成 COM 组件的互操作](http://msdn.microsoft.com/en-us/7a2c657a-cfef-40f0-bed3-7c2c0ac4abdf)   
 [托管的 VSPackage](../misc/managed-vspackages.md)