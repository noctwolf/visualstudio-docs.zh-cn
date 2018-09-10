---
title: 注册的自定义调试引擎 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c87b3749c2ea63e89e2e8fb0caf773434a38df2
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281385"
---
# <a name="register-a-custom-debug-engine"></a>注册自定义调试引擎
调试引擎必须将自身注册为一个类工厂，以下 COM 约定，以及通过 Visual Studio 注册通过 Visual Studio 注册表子项。  
  
> [!NOTE]
>  您可以找到举例说明如何注册在 TextInterpreter 示例中，作为一部分生成的调试引擎[教程： 生成调试引擎使用 ATL COM](https://msdn.microsoft.com/library/9097b71e-1fe7-48f7-bc00-009e25940c24)。  
  
## <a name="dll-server-process"></a>DLL 服务器进程  
 调试引擎是通常设置在其自己的 DLL 中作为 COM 服务器。 在这种情况下，调试引擎必须注册类工厂的 CLSID COM Visual Studio 才能访问它。 然后，调试引擎必须注册自身建立任何属性 （也称为度量值） 的 Visual Studio 调试引擎支持。 度量值写入到 Visual Studio 注册表子项的选择取决于调试引擎支持的功能。  
  
 [用于调试的 SDK 帮助程序](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)介绍了不唯一的注册表位置必须注册的调试引擎; 它还介绍了*dbgmetric.lib*库，其中包含许多有用的功能和声明为使操作更容易注册表的 c + + 开发人员。  
  
### <a name="example"></a>示例  
 下面的示例 （摘自 TextInterpreter 示例） 演示如何使用`SetMetric`函数 (从*dbgmetric.lib*)，以注册 Visual Studio 调试引擎。 中也定义了所传递的指标*dbgmetric.lib*。  
  
> [!NOTE]
>  TextInterpreter 是一种基本的调试引擎;它未设置，并因此不会注册 — 任何其他功能。 更完整的调试引擎必须一整个系列`SetMetric`调用或其等效项，一个用于调试引擎的每个功能支持。  
  
```  
// Define base registry subkey to Visual Studio.  
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";  
  
HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)  
{  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);  
  
    return base::RegisterServer(bRegTypeLib, pCLSID);  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [用于调试的 SDK 帮助程序](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [教程： 构建使用 ATL COM 的调试引擎](https://msdn.microsoft.com/library/9097b71e-1fe7-48f7-bc00-009e25940c24)