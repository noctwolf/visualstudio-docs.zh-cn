---
title: "在 Visual Studio 中使用 Python 步骤 5 | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: 69e51c46-9a10-4d6f-9f74-2d1385beb1ac
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 30f89023d09ab90cae2698de976eaef44165b0fb
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2017
---
# <a name="step-5-installing-packages-in-your-python-environment"></a>步骤 5：在 Python 环境中安装程序包

**上一步：[在调试器中运行代码](vs-tutorial-01-04.md)**

Python 开发者社区制作了数千个有用的程序包，用户可以将它们合并到自己的项目中。 Visual Studio 提供一个 UI，用于管理 Python 环境中的程序包。

1. 选择“查看”>“其他窗口”>“Python 环境”菜单命令。 “Python 环境”窗口作为解决方案资源管理器的同级打开，并向用户显示各种可用的环境。 列表中包含使用 Visual Studio 安装程序安装的环境以及单独安装的环境。 粗体显示的环境是用于新项目的默认环境。

  ![“Python 环境”窗口](media/environments-default-view-blue.png)

1. 通过环境的“概述”选项卡，可以快速访问该环境的交互窗口以及安装文件夹和解释器。 例如，选择“打开交互窗口”，会在 Visual Studio 中显示该特定环境的交互窗口。

1. 选择“程序包”选项卡，会显示环境中当前安装的程序包列表。

  ![环境中安装的程序包](media/environments-installed-packages-blue.png)

1. 安装 `matplotlib`，方法如下：在搜索字段中输入其名称，然后选择 `pip install`

  ![在环境中安装 matplotlib](media/environments-add-matplotlib1.png)

1. 如果系统提示同意提升，请同意。
 
1. 安装程序包后，它会显示在“Python 环境”窗口中。 单击程序包右侧的 **X** 可卸载它。 

  ![在环境中完成 matplotlib 的安装](media/environments-add-matplotlib2.png)

  环境下方的小进度条指示 Visual Studio 正在为新安装的程序包生成 IntelliSense 数据库。 “IntelliSense”选项卡也显示了更多详细信息。 请注意，完成该数据库之前，编辑器中的自动完成和语法检查等 IntelliSense 功能针对该程序包处于非活动状态。

1. 通过选择“文件”>“新建”>“项目”创建新项目，然后选择“Python 应用程序”模板。 在随即出现的代码文件中，粘贴以下代码，以创建像之前的教程步骤一样的余弦波，只不过这次以图形方式绘制：

    ```python  
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt
    from math import radians

    def main():  
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()
                    
    main()
    ```  

1. 按 (F5)（有调试器）或 (Ctrl+F5)（没有调试器）运行程序以查看输出：

  ![matplotlib 示例的输出](media/environments-add-matplotlib3.png)


## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [使用 Git](vs-tutorial-01-06.md)

### <a name="going-deeper"></a>深入了解
- [Python 环境](python-environments.md)
