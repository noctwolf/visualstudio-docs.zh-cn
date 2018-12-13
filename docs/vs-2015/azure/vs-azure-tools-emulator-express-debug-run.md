---
title: 使用 Emulator Express 运行和调试本地计算机上的 Azure 云服务 |Microsoft Docs
description: 使用 Emulator Express 运行和调试本地计算机上的云服务
author: mikejo5000
manager: douge
ms.assetid: 73108f98-a552-4817-b7a1-551367b71906
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 03/06/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 28dd59e3d691df0199afffe93d68d60668c6afe4
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001268"
---
# <a name="using-emulator-express-to-run-and-debug-an-azure-cloud-service-on-a-local-machine"></a>使用快速仿真器在本地计算机上运行和调试 Azure 云服务
通过使用 Emulator Express，可以测试和调试云服务而无需以管理员身份运行 Visual Studio。 可以设置项目设置以使用 Emulator Express 或完整仿真程序，具体取决于你的云服务的要求。 有关完整模拟器的详细信息，请参阅[在计算模拟器中运行 Azure 应用程序](/azure/storage/common/storage-use-emulator)。

## <a name="using-emulator-express-in-visual-studio"></a>在 Visual Studio 中使用 Emulator Express
创建在 Azure SDK 2.3 或更高版本的 Azure 项目时，会自动使用 Emulator Express。 对于使用早期版本的 Azure SDK 创建的现有项目，使用以下步骤来选择 Emulator Express:

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**属性**。

1. 在项目属性页中，选择**Web**选项卡。

    ![Azure 云服务项目的属性](./media/vs-azure-tools-emulator-express-debug-run/web-properties.png)

1. 下**本地开发服务器**，选择**使用 IIS Express 选项**。

1. 下**模拟器**，选择**使用 Emulator Express**。
   
1. 若要启动 Emulator Express，请在命令提示符处运行以下命令： 

    ```
    csrun.exe /useemulatorexpress
    ```

## <a name="emulator-express-limitations"></a>Emulator Express 限制
以下问题是已知 Emulator Express 的限制： 

- Emulator Express 是不与 IIS Web 服务器兼容。
- 你的云服务可以包含多个角色，但每个角色都只能有一个实例。
- 无法访问 1000年以下的端口号。 如果使用的身份验证提供程序通常使用低于 1000年的端口，可能需要将此值更改为 1000年以上的端口号。
- 适用于 Azure 计算仿真程序的任何限制也适用于 Emulator Express。 例如，不能具有超过 50 个角色实例，每个部署。 有关 Azure 计算模拟器的详细信息，请参阅[在计算模拟器中运行 Azure 应用程序](http://go.microsoft.com/fwlink/p/?LinkId=623050)。

## <a name="next-steps"></a>后续步骤
[调试 Azure 云服务](https://msdn.microsoft.com/library/azure/ee405479.aspx)
