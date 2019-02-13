---
title: 加载项目的子集
ms.date: 12/04/2018
ms.prod: visual-studio-dev16
ms.topic: conceptual
helpviewer_keywords:
- filtered solution
- solution filtering
author: gewarren
ms.author: stsu
manager: jillfra
monikerRange: '>= vs-2019'
ms.openlocfilehash: 2f7163ecda377d8fa8b7c27ed50dae4068d39600
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55952913"
---
# <a name="filtered-solutions-in-visual-studio"></a>Visual Studio 中筛选的解决方案

**Visual Studio 2019 预览版 1 中的新增功能**

大型开发团队通常使用包含许多项目的单个大型解决方案进行协作。 但是，个别开发人员通常只处理这些项目的一小部分。 为了在打开大型解决方案时提高性能，Visual Studio 2019 预览版 1 中引入了解决方案筛选。 通过解决方案筛选，可打开仅加载选择性项目的解决方案。 在解决方案中加载项目子集可以减少解决方案加载、构建和测试运行时间，并实现更有针对性的审查。

可以使用以下功能：

- 通过在不加载任何项目的情况下打开解决方案，可以更快获得代码。 解决方案打开后，可以有选择地选择要加载的项目。

- 重新打开解决方案时，Visual Studio 会记住在上一个会话中加载的项目，并仅加载这些项目。

- 可以创建解决方案筛选器文件以保存一个或多个项目加载配置或与队友共享配置。

## <a name="open-a-filtered-solution"></a>打开已筛选的解决方案

要打开仅加载了某些项目的解决方案，请执行以下步骤：

1. 在菜单栏上，依次选择“文件” > “打开” > “项目/解决方案”。

2. 在“新建项目”对话框中，选择解决方案，然后选择“不加载项目”。

   ![Visual Studio 的“打开项目”对话框，其中已选中“不加载项目”](media/filtered-solutions/do-not-load-projects.png)

3. 选择“打开”。

   解决方案打开，其中已卸载其所有项目。

4. 在“解决方案资源管理器”中，选择要加载的项目（按住 Ctrl 同时单击以选择多个项目），然后右键单击项目并选择“重新加载项目”。

   ![在 Visual Studio 解决方案资源管理器重新加载多个项目](media/filtered-solutions/reload-project.png)

   Visual Studio 将记住下次在本地打开解决方案时要加载的项目。

## <a name="toggle-unloaded-project-visibility"></a>切换已卸载的项目可见性

可以选择在“解决方案资源管理器”中使用以下选项之一查看解决方案中的所有项目或仅查看已加载的项目：

- 右键单击解决方案，然后选择“显示已卸载的项目”或“隐藏已卸载的项目”。

- 选择“显示所有文件”按钮来切换已卸载项目的可见性。

   ![Visual Studio“解决方案资源管理器”中的“显示所有文件”按钮](media/filtered-solutions/show-all-files.PNG)

## <a name="solution-filter-files"></a>解决方案筛选器文件

如果要共享项目加载配置或将其提交给源代码管理，则可以创建解决方案筛选器文件（扩展名为 .slnf）。 打开解决方案筛选器文件时，解决方案将在 Visual Studio 中打开，其中已加载指定的项目并已隐藏所有卸载的项目。 可以[切换](#toggle-unloaded-project-visibility)以查看已卸载的项目。

从外观来看，解决方案筛选器文件与常规解决方案文件不同，前者在“解决方案资源管理器”的解决方案旁附加了一个漏斗字形图标。 筛选器的名称和已加载项目的数量也显示在解决方案名称旁边。

![在 Visual Studio 解决方案资源管理器中打开的解决方案筛选器文件](media/filtered-solutions/solution-filter.PNG)

> [!NOTE]
> 如果在创建解决方案筛选器文件后将新项目添加到原始解决方案，则它们在“解决方案资源管理器”中显示为已卸载的项目。

### <a name="create-a-solution-filter-file"></a>创建解决方案筛选器文件

1. 在“解决方案资源管理器”中，右键单击“解决方案”，然后选择“另存为解决方案资源管理器筛选器”。

   ![Visual Studio 解决方案资源管理器中的“另存为解决方案资源管理器筛选器”菜单](media/filtered-solutions/save-as-solution-filter.png)

2. 选择解决方案筛选器文件的名称和位置。

创建解决方案筛选器文件后，它会添加到你的“最近项目和解决方案”列表中，以便访问：

![在 Visual Studio 中打开最近文件](media/filtered-solutions/open-recent.png)

## <a name="see-also"></a>请参阅

- [在解决方案资源管理器中自定义文件嵌套](file-nesting-solution-explorer.md)
- [优化 Visual Studio 性能](optimize-visual-studio-performance.md)