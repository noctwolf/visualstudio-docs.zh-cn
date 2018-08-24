---
title: 如何：打开多个解决方案
description: 了解如何打开 Visual Studio for Mac 中的多个解决方案以及如何打开应用程序的多个实例。
author: asb3993
ms.author: amburns
ms.date: 07/19/2018
ms.assetid: 592BA4E3-8DEF-4FCD-8BA0-519A4CEEE03E
ms.openlocfilehash: 85d300c5131dad2d6f4480fceb4770e2e8a126a5
ms.sourcegitcommit: b544e2157ac20866baf158eef9cfed3e3f1d68b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2018
ms.locfileid: "39388489"
---
# <a name="opening-multiple-solutions-or-instances-of-visual-studio-for-mac"></a>打开 Visual Studio for Mac 的多个解决方案或实例

默认情况下，Mac 上的所有应用程序（包括 Visual Studio for Mac）都是单实例应用。 这意味着如果要使用的应用程序已经打开（通过停靠栏中图标下方的“点”说明），再次单击该图标将打开正在运行的实例，而不是新实例。  如果需要应用程序的其他实例，可提示系统打开，如[下一部分](#open-a-second-instance-of-visual-studio-for-mac)中所述。

此外，打开解决方案时，默认行为是在新工作区中打开解决方案并关闭当前工作区（如有必要）。 可通过保持当前工作区打开来替代此默认行为，如[打开第二个解决方案](#open-a-second-solution-inside-a-single-instance)部分中所述。

## <a name="open-a-second-instance-of-visual-studio-for-mac"></a>打开 Visual Studio for Mac 的第二个实例

要打开 IDE 的第二个实例，请打开终端应用程序并输入以下行：

```bash
open -n "/Applications/Visual Studio.app"
```

## <a name="open-a-second-solution-inside-a-single-instance"></a>在单实例中打开第二个解决方案

要在第一个解决方案旁边打开第二个解决方案，请使用以下步骤：

1. 打开第一个解决方案后，依次选择“文件”>“打开”。
2. 浏览文件系统，查找现有解决方案。
3. 选择 .sln 文件，然后按“选项”按钮：
    
    ![“选项”按钮的位置](media/open-multiple-solutions-image3.png)
4. 取消选中“关闭当前工作区”框：

    ![当前工作区的屏幕截图](media/open-multiple-solutions-image1.png)

1. 按“打开”按钮在 Solution Pad 中打开第二个解决方案。

或者，如果最近打开了解决方案，可使用以下步骤：

1. 转到“文件”>“最近解决方案”菜单项：

    ![“最近解决方案”菜单的屏幕截图](media/open-multiple-solutions-image2.png)

1. 按住 Ctrl 键并选择解决方案。 此组合可打开 Solution Pad 中的第二个解决方案。
