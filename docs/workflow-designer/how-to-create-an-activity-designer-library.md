---
title: "如何： 创建活动设计器库 |Microsoft 文档"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5b62e092-63b3-462d-9d77-fb112482f45d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 0f257aabb4b1c2c1b1dce05e34273dc303a8f7da
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-an-activity-designer-library"></a>如何：创建活动设计器库
使用自定义活动设计器可为标准或自定义活动创建一个用户界面。 您可控制该用户界面的复杂度并且可为一个活动创建多个活动设计器。 此方案使您能创建适合多种受众的设计器。

### <a name="to-create-an-activity-designer-library"></a>创建活动设计器库

1.  启动 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]。

2.  上**文件**菜单上，指向**新建**，然后选择**项目...**以打开**新项目**对话框。

3.  在**项目类型**窗格中，选择**工作流**从**Visual C#**或**Visual Basic**具体取决于你首选的分组语言。

4.  在**模板**窗格中，选择**活动设计器库**。

5.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

6.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

7.  在**解决方案**框中，键入你的解决方案的描述性名称，然后单击**确定**。

    > [!NOTE]
    > 如果你想要添加到现有的解决方案的工作流控制台应用程序，打开该解决方案中的[!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]，右键单击中的解决方案**解决方案资源管理器**，然后选择**添加**，然后**新项目...**以打开**新项目**对话框。 按照此过程中的上述步骤继续操作。

8.  该项目模板将在 XAML 中创建一个活动设计器定义并在源代码中创建代码隐藏实现文件。 Windows 工作流设计器将打开并显示活动设计器画布。

9. 拖动[!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)]控件从**工具箱**到设计图面可在你自定义活动设计器中使用它们。  有关如何实现一个自定义活动设计器的示例，请参阅[如何： 创建自定义活动设计器](/dotnet/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer)。

    > [!WARNING]
    > 自定义活动设计器可以用于自定义活动以及默认[!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)]活动。

## <a name="see-also"></a>请参阅

- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)