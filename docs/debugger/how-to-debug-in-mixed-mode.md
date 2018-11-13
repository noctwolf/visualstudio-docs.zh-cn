---
title: 如何： 在混合模式调试 |Microsoft Docs
ms.custom: ''
ms.date: 11/05/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ef87a1f9fd90395a9a1f5c99ad6e8090b13304e
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295470"
---
# <a name="how-to-debug-in-mixed-mode"></a>如何： 在混合模式下调试
以下过程介绍如何为托管和本机代码组合在一起，也称为混合模式调试启用调试。 有两个混合模式调试方案：  
  
- 在本机代码中，编写调用 DLL 的应用和托管 DLL。 
  
- 调用 DLL 的应用编写托管代码中，DLL 是本机代码中。 本教程将指导你完成此方案的详细信息，请参阅[调试托管和本机代码](../debugger/how-to-debug-managed-and-native-code.md)。
   
可以让调用应用程序项目中的托管和本机调试器**属性**页。 设置本机和托管应用程序之间存在差异。 

如果没有向调用应用程序的项目的访问权限，则可以调试 DLL 项目的 DLL。 您不需要混合的模式调试只是 DLL 项目。 有关详细信息，请参阅[如何： 从 DLL 项目调试](../debugger/how-to-debug-from-a-dll-project.md)。 

> [!NOTE]
> 对话框和命令可能与本文中，具体取决于您的 Visual Studio 设置或版本中的不同。 若要更改您的设置，请选择**工具** > **导入和导出设置**。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)。

## <a name="enable-mixed-mode-debugging-for-a-native-calling-app"></a>启用混合模式调试调用的本机应用  
  
1. 选择中的 c + + 项目**解决方案资源管理器**然后单击**属性**图标中，按**Alt**+**Enter**，或右键单击并选择**属性**。
   
1. 在中**\<项目 > 属性页**对话框中，展开**配置属性**，然后选择**调试**。  
   
1. 设置**调试器类型**到**混合**或**自动**。
   
1. 选择“确定”。
   
   ![启用混合的模式调试](../debugger/media/dbg-mixed-mode-from-native.png "启用混合的模式调试")

## <a name="enable-mixed-mode-debugging-for-a-managed-calling-app"></a>启用混合模式调试托管的调用应用程序  
  
1. 选择中的 C# 或 Visual Basic 项目**解决方案资源管理器**，然后选择**属性**图标中，按**Alt**+**Enter**，或右键单击，然后选择**属性**。
   
1. 选择**调试**选项卡，然后选择**启用本机代码调试**。
   
1. 关闭属性页以保存所做的更改。

   ![启用本机代码调试](../debugger/media/dbg-mixed-mode-from-csharp.png "启用本机代码调试")
  
>[!NOTE]
>在大多数版本的 Visual Studio 2017，你必须使用*launchSettings.json*文件而不是项目属性以启用混合模式调试的.NET Core 应用中的本机代码。 有关详细信息，请参阅[调试托管和本机代码](../debugger/how-to-debug-managed-and-native-code.md)。

## <a name="see-also"></a>请参阅  
 [如何：从 DLL 项目进行调试](../debugger/how-to-debug-from-a-dll-project.md)