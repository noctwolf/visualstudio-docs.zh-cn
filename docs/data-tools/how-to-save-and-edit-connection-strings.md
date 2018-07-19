---
title: 如何：保存和编辑连接字符串
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f8ef3a2c-029c-423b-9d9e-a4f1add4f640
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 050d5f7bcda86890642a5bef10fa04d2c12b4203
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089226"
---
# <a name="how-to-save-and-edit-connection-strings"></a>如何： 保存和编辑连接字符串
在 Visual Studio 应用程序中的连接字符串是保存在应用程序配置文件 （也称为应用程序设置） 或直接在您的应用程序中硬编码。 在应用程序配置文件中保存连接字符串简化了维护应用程序的任务。 如果需要更改连接字符串，您可以在应用程序设置文件 （而不是无需在源代码中进行更改并重新编译应用程序） 中更新它。

将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 保存在应用程序配置文件中的连接字符串是未经加密处理的，因此其他人有可能访问该文件并查看其内容。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 集成安全性。

如果不选择使用 Windows 集成安全性，并且数据库需要用户名和密码，则可以在连接字符串中省略这些内容，但需要应用程序提供此信息才能成功连接到数据库。 例如，可以创建一个对话框提示用户提供此信息并在运行时动态生成连接字符串。 如果在发送到数据库的途中该信息被截获，则安全性将得不到保证。
有关详细信息，请参阅[保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。

## <a name="to-save-a-connection-string-from-within-the-data-source-configuration-wizard"></a>若要保存从数据源配置向导中的连接字符串
在中**数据源配置向导**，选择选项以在保存连接**将连接字符串保存到应用程序配置文件**页。

## <a name="to-save-a-connection-string-directly-into-application-settings"></a>将连接字符串直接保存到应用程序设置中
1. 在中**解决方案资源管理器**，双击**我的项目**图标 (Visual Basic) 或**属性**图标 (C#) 以打开**项目设计器**.
1. 选择**设置**选项卡。
1. 输入**名称**连接字符串。 当在代码中访问该连接字符串时引用此名称。
1. 设置**类型**到 (**连接字符串**)。
1. 将保留**作用域**设置为**应用程序**。
1. 键入连接字符串**值**字段中，或单击**省略号**中的 （...） 按钮**值**字段，打开**连接属性**对话框生成连接字符串。

## <a name="edit-connection-strings-stored-in-application-settings"></a>编辑应用程序设置中存储的连接字符串
你可以修改保存在应用程序设置中使用的连接信息**项目设计器**。

### <a name="to-edit-a-connection-string-stored-in-application-settings"></a>编辑存储在应用程序设置中的连接字符串
1. 在中**解决方案资源管理器**，双击**我的项目**图标 (Visual Basic) 或**属性**图标 (C#) 以打开**项目设计器**.
1. 选择**设置**选项卡。
1. 找到你想要编辑和选择的文本中的连接**值**字段。
1. 编辑中的连接字符串**值**字段中，或单击**省略号**中的 （...） 按钮**值**要编辑与的连接字段**连接属性**对话框。

## <a name="edit-connection-strings-for-datasets"></a>编辑数据集的连接字符串
可以修改在数据集中每个 TableAdapter 的连接信息。

### <a name="to-edit-a-connection-string-for-a-tableadapter-in-a-dataset"></a>若要编辑的连接字符串中数据集的 TableAdapter
1. 在中**解决方案资源管理器**，双击数据集 (**.xsd**文件)，其想要编辑的连接。
1. 选择**TableAdapter**有想要编辑的连接或查询。
1. 在中**属性**窗口中，展开**连接节点**。
1. 若要快速修改连接字符串，请编辑**ConnectionString**属性，或单击向下箭头**连接**属性，然后选择**新连接**。

## <a name="security"></a>安全性
将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。 若要控制对数据库的访问，一种较为安全的方法是使用 Windows 集成安全性。
有关详细信息，请参阅[保护连接信息](/dotnet/framework/data/adonet/protecting-connection-information)。

## <a name="see-also"></a>请参阅

- [添加连接](../data-tools/add-new-connections.md)