---
title: "快速入门 - 在 Visual Studio 中使用模板创建 Python 项目 | Microsoft Docs"
description: "通过使用其中一个内置模板创建 Visual Studio 项目，使用 Python 快速入门。"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 648c1e2b4ee3a5c9bc10d74ee384a08bc5ddce64
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2018
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>快速入门：从 Visual Studio 中的模板创建 Python 项目

[在 Visual Studio 2017 中安装 Python 支持](installing-python-support-in-visual-studio.md)后，就可以使用各种模板轻松创建新的 Python 项目。

1. 启动 Visual Studio。

1. 选择“文件”>“新建”>“项目”(Ctrl+Shift+N)。 在“新建项目”对话框中，搜索“Python”，然后选择所需的模板。 请注意，选择模板时会显示模板提供内容的简短说明。 （另请参阅 [Python 项目](managing-python-projects-in-visual-studio.md#project-templates)。）

    ![显示 Python 模板的 VS2017“新建项目”对话框](media/projects-new-project-dialog2.png)

1. 在本快速入门教程中，选择“Python 应用程序”模板，为项目指定名称（比如“MakePI”）和位置，然后选择“确定”。

1. Visual Studio 随即创建项目文件（磁盘上的 `.pyproj` 文件）以及模板所述的任何其他文件。 使用“Python 应用程序”模板时，项目仅包含一个与项目同名的空文件。 默认情况下，该文件在 Visual Studio 编辑器中打开。

    ![使用“Python 应用程序”模板时生成的项目](media/projects-new-structure.png)

1. 向打开的文件添加一段代码，比如下面用于计算并显示 PI 1000 位数的代码：

    ```python
    """ Print digits of PI; code adapted from the second, shorter solution
    at http://www.codecodex.com/wiki/Calculate_digits_of_pi#Python
    """

    from time import perf_counter

    def pi_digits_Python(digits):
        scale = 10000
        maxarr = int((digits / 4) * 14)
        arrinit = 2000
        carry = 0
        arr = [arrinit] * (maxarr + 1)
        output = ""

        for i in range(maxarr, 1, -14):
            total = 0
            for j in range(i, 0, -1):
                total = (total * j) + (scale * arr[j])
                arr[j] = total % ((j * 2) - 1)
                total = total / ((j * 2) - 1)

            output += "%04d" % (carry + (total / scale))
            carry = total % scale

        return output;

    def test_py():
        digits = 1000;

        start = perf_counter()
        output = pi_digits_Python(digits);
        elapsed = perf_counter() - start;

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py();
    ```

1. 按 Ctrl+F5 或选择菜单上的“调试”>“开始执行(不调试)”运行程序。 结果显示在控制台窗口中。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [教程：在 Visual Studio 中使用 Python](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>请参阅

- [手动标识现有的 Python 解释器](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment)。
- [在 Visual Studio 2015 及更早版本中安装 Python 支持](installing-python-support-in-visual-studio.md)。
- [安装位置](installing-python-support-in-visual-studio.md#install-locations)。
