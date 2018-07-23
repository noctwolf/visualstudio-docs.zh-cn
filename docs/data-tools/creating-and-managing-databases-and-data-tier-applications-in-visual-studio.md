---
title: 数据库项目、 服务器项目和 Visual Studio 中的 DAC 项目
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managing change, databases
- database features of Visual Studio, managing change
- databases, managing change
- managing change, database servers
ms.assetid: 40b51f5a-d52c-44ac-8f84-037a0917af33
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 6ca08103614989ddbfd096a08a1531e756c9f67c
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176097"
---
# <a name="database-projects-and-data-tier-applications-in-visual-studio"></a>数据库项目和 Visual Studio 中的数据层应用程序

可以使用数据库项目来创建新数据库，新的数据层应用程序 (Dac)，以及更新现有数据库和数据层应用程序。 数据库项目和 DAC 项目，可以大致相同的方式将这些技术应用于托管或本机代码中将版本控制和项目管理技术应用于进行数据库开发工作。 可帮助开发团队创建 DAC 项目中，数据库项目或服务器项目并将其置于版本控制之下的管理对数据库和数据库服务器的更改。 然后，您的团队成员可以签出文件，以使、 生成和测试中隔离的开发环境或沙盒，做的更改，与团队共享它们之前。 若要帮助确保代码质量，你的团队可以完成并部署到生产环境的更改之前在过渡环境中测试的特定版本的数据库的所有更改。

有关支持的数据层应用程序的数据库功能的列表，请参阅[数据层应用程序中支持的功能](/previous-versions/visualstudio/visual-studio-2010/ee362013(v=vs.100))。 如果您使用您的数据库不支持的数据层应用程序的功能，您应改用数据库项目来管理对你的数据库的更改。

## <a name="common-high-level-tasks"></a>常见的高级任务

|高级任务|支持内容|
|----------------------|------------------------|
|**开始进行开发的数据层应用程序：** DAC 是随引入的新概念[!INCLUDE[sskatmai_r2](../data-tools/includes/sskatmai_r2_md.md)]，其中包含用于定义[!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]数据库和支持实例使用的客户端-服务器或第 3 层对象应用程序。 DAC 包括数据库对象，如表和视图，以及实例实体，例如登录名。 可以使用 Visual Studio 创建一个 DAC 项目，生成一个 DAC 包文件，并将该 DAC 包文件发送到部署到的实例上的数据库管理员[!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]数据库引擎。|-   [创建和管理数据层应用程序](http://go.microsoft.com/fwlink/?LinkId=160741)<br />-   [SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=227328)|
|**执行迭代数据库开发：** 如果你是开发人员或测试人员，签出项目的部分，然后在隔离的开发环境中更新它们。 通过使用此类型的环境，可以测试所做的更改，而不影响其他团队的成员。 所做的更改完成后，您将签入版本控制，其他团队成员可以获取所做的更改和生成并将其部署到测试服务器文件。|-   [查询和文本编辑器 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327)<br />-   [TRANSACT-SQL 调试器](http://go.microsoft.com/fwlink/?LinkId=227324)|
|**原型制作，验证测试结果和修改数据库脚本和对象：** 可以使用[!INCLUDE[tsql](../data-tools/includes/tsql_md.md)]编辑器来执行这些常见任务之一。|-   [查询和文本编辑器 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=227327)|

## <a name="see-also"></a>请参阅

- [适用于 NET 的 Visual Studio Data Tools](../data-tools/visual-studio-data-tools-for-dotnet.md)
