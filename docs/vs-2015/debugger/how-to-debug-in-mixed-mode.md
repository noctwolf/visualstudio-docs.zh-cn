---
title: 如何： 在混合模式调试 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6ee85e5822d4792046c755c85d699dd6a9a5d26
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51737165"
---
# <a name="how-to-debug-in-mixed-mode"></a>How to: Debug in Mixed Mode
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

以下过程描述如何调试托管代码和本机代码，这一过程也称作混合模式调试。 根据 DLL 或应用程序是否用本机代码编写，有两种方案可以用来进行调试：  
  
-   调用 DLL 的调用应用程序是用本机代码编写的。 在这种情况下 DLL 是托管的，托管调试器和本机调试器都必须启用，以调试托管代码和本机代码。 您可以将此签入**\<项目 > 属性页**对话框。 具体如何检查取决于是从 DLL 项目中启动调试，还是从调用应用程序项目中启动调试。  
  
-   调用 DLL 的调用应用程序是用托管代码编写的，而 DLL 是用本机代码编写的。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-enable-mixed-mode-debugging"></a>启用混合模式调试  
  
1.  在中**解决方案资源管理器**，选择的项目。  
  
2.  上**视图**菜单上，单击**属性页**。  
  
3.  在中**\<项目 > 属性页**对话框中，展开**配置属性**节点，，然后选择**调试**。  
  
4.  设置**调试器类型**到**混合**或**自动**。  
  
## <a name="see-also"></a>请参阅  
 [How to: Debug from a DLL Project](../debugger/how-to-debug-from-a-dll-project.md)



