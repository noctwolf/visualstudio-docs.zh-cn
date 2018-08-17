---
ms.topic: include
ms.openlocfilehash: ff6523d33e29f4fcc6fd02c08e0a35ac00892829
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39638386"
---
### <a name="create-a-project-using-django-20"></a>使用 Django 2.0 创建项目

目前，Blank Django Web 项目模板使用最新的 Django 1.x 版本。 若要使用 Django 2.x，最快方式是将 Django 2.x 文件导入到 Django 1.x 项目中。 通过遵循该过程，可以充分利用由 Visual Studio 项目模板处理的其他详细信息。

1. 使用“Blank Django Web 项目”模板创建 Django 1.x 项目，如前一部分中所述。 但是，在“此项目需要外部依赖项”提示符下，选择“我将自行安装”。 选择此选项可避免安装在后续步骤中卸载的依赖项。

1. 打开命令提示符，然后导航到临时文件夹。

1. 运行 `pip install django`，在全局 Python 环境中安装最新的 Django 包。

1. 运行 `django-admin startproject <project_name>`，将 `<project_name>` 替换为在步骤 1 中使用的同一项目名称，如“HelloDjango”。 `startproject` 命令会创建 manage.py 文件和与 `<project_name>` 匹配的文件夹，其中包含以下文件：init.pysettings.py、urls.py 和 wsgi.py。*\_\_\_\_*

1. 在 Visual Studio 中，将项目中的 Django 1.x 文件替换为 Django 2.x 文件，如下所示：

    1. 在“解决方案资源管理器”中，删除 manage.py 和 Django 应用文件夹。
    1. 右键单击项目，选择“添加” > “现有项...”命令，导航到在步骤 4 中创建的 manage.py 文件并选中它，然后选择“确定”。 Visual Studio 随即会将该文件复制到项目。
    1. 再次右键单击项目，选择“添加” > “现有文件夹...”命令，导航到在步骤 4 中创建的应用文件夹并选中它，然后选择“确定”。 Visual Studio 随即会将整个文件夹及其四个文件复制到项目。
    1. 右键单击 manage.py，然后选择“设置为启动文件”。

    > [!Important]
    > 在 Visual Studio 项目中显示的应用名称必须匹配与 `django-admin` 实用工具配合使用的 `<project_name>`，因为该实用工具将此名称用作 Python 代码文件内的命名空间。

1. 打开 requirements.txt，将其内容更改为 `django >=2.0, <3`，并保存该文件。

1. 在“解决方案资源管理器”中，右键单击“Python 环境”节点并选择“添加虚拟环境”。 接受显示的对话框中的默认设置，并选择“创建”。 接受任何有关管理员权限的提示。