---
title: "快速入门：在 Visual Studio 中克隆 Python 代码存储库 | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: 5ce79d4e8ff2056b5d713eaa781b22359141c9b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>快速入门：在 Visual Studio 中克隆 Python 代码存储库

[在 Visual Studio 2017 中安装 Python 支持](installation.md)后，就可以轻松地克隆 Python 代码存储库并从中创建项目。

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

2. 启动 Visual Studio。

3. 选择“视图”>“团队资源管理器...”，打开“团队资源管理器”窗口，可在该窗口中连接到 GitHub 或 Visual Studio Team Services，或者克隆存储库。

    ![显示 Visual Studio Team Services、GitHub 并克隆存储库的“团队资源管理器”窗口](media/team-explorer.png)

4. 在“本地 Git 存储库”下的 URL 字段中，输入 `https://github.com/gregmalcolm/python_koans`，为克隆文件输入一个文件夹，然后选择“克隆”。

    > [!Tip]
    > 在团队资源管理器中指定的文件夹是用于接收克隆文件的特定文件夹。 与 `git clone` 命令不同，在团队资源管理器中创建克隆时不会使用存储库名称自动创建一个子文件夹。

5. 完成克隆后，双击团队资源管理器底部的存储库文件夹，导航到存储库仪表板。 在“解决方案”下方，选择“新建...”。

    ![“团队资源管理器”窗口, 从克隆创建新项目](media/team-explorer-new-project.png)

6. 在随即出现的“新建项目”对话框中，选择“从现有的 Python 代码”，为项目指定名称，将“位置”设置为与存储库相同的文件夹，并选择“确定”。 在随即出现的向导中选择“完成”。

7. 从菜单中选择“视图”>“解决方案资源管理器”。

8. 在解决方案资源管理器中，展开 `python3` 节点，右键单击 `contemplate_koans.py`，然后选择“设置为启动文件”。 此步骤指示 Visual Studio 在运行项目时应使用哪个文件。

9. 从菜单中选择“项目”>“属性”，选择“常规”选项卡，将“工作目录”设置为“python3”。 此步骤是必需的，因为 Visual Studio 默认将工作目录设置为项目根目录，而非启动文件所在的位置（`python3\contemplate_koans.py`，也可以在项目属性中看到）。 程序代码会在工作文件夹中查找文件 `koans.txt`，因此不更改此值会导致运行时错误。

    ![设置 Python 项目的工作目录](media/projects-set-working-directory.png)

10. 按 Ctrl+F5 或选择“调试”>“开始执行(不调试)”运行程序。 如果在 `koans.txt` 中看到 `FileNotFoundError`，则重新检查上一步中的工作目录设置。

11. 程序成功运行时，会在 `python3/koans/about_asserts.py` 的第 17 行显示一个断言错误。 这是有意为之：程序旨在通过让用户更正所有故意设计的错误来学习 Python。 （[Ruby Koans](http://rubykoans.com/) 上提供了更多详细信息，Python Koans 的设计灵感便源于前者。）

    ![Python koans 程序的第一次输出](media/koans-output.png)

12. 通过在解决方案资源管理器中导航到 `python3/koans/about_asserts.py` 并双击，打开该文件。 请注意，编辑器中默认不显示行号。 若要更改此设置，请选择“工具”>“选项”，选择对话框底部的“显示所有设置”，然后导航到“文本编辑器”>“Python”>“常规”并选择“行号”：

    ![为 Python 文件启用行号](media/options-general-line-numbers.png)

13. 通过将第 17 行的 `False` 参数更改为 `True` 来更正错误。 该行应如下所示：

    ```python
    self.assertTrue(True) # This should be True
    ```

14. 再次运行程序，确保第一次检查顺利通过，程序在下一个 koan 处停止。 继续更正错误，然后根据需要重新运行程序。

> [!Important]
> 在本快速入门教程中，创建了对 GitHub 上 *python_koans* 存储库的直接克隆。 此类存储库的作者会对其设置保护，不允许直接更改，因此尝试将更改提交到存储库会失败。 在实际操作中，开发者会将此类存储库分叉到自己的 GitHub 帐户，在那里进行更改后，再创建拉取请求将这些更改提交到原始存储库。 [教程步骤 6：使用 Git](vs-tutorial-01-06.md) 介绍了这些步骤。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [教程：在 Visual Studio 中使用 Python](vs-tutorial-01-01.md)

## <a name="see-also"></a>请参阅

- [为现有 Python 解释器创建环境](python-environments.md#creating-an-environment-for-an-existing-interpreter)。
- [在 Visual Studio 2015 及更早版本中安装 Python 支持](installation.md)。
- [安装位置](installation.md#install-locations)。
