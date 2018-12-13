---
title: 如何： 管理你的项目中的本地数据文件 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.data.LocalConnectionConverter
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- mdf files
- local data
- .mdb files
- .mdf files
- data [Visual Studio], local
- mdb files
ms.assetid: 3ffa1aa9-17e4-422c-a02f-09224828cdfc
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.openlocfilehash: 16e2d38dda97bd8a7f130254b2f23be9f17e0ac4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49271370"
---
# <a name="how-to-manage-local-data-files-in-your-project"></a>如何：管理项目中的本地数据文件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本地数据库文件可以包含一个项目中的文件。 第一次连接到本地数据库文件，您可以选择在项目中创建一个副本或连接到其当前位置中的现有文件。 如果您连接到现有文件，它会保留在其原始位置。 如果您选择将文件复制到你的项目，Visual Studio 会创建一份、 将其添加到你的项目，并修改要指向的副本的连接。 此外会修改其他连接，如服务器资源管理器中。  
  
 属性的默认设置取决于正在使用的数据库文件的类型。 行为**复制到输出目录**属性不适用于 Web 或 c + + 项目。  
  
 在开发期间，可能想要在数据库上查看你的代码的效果，而无需进行这些更改永久。 您可以通过设置来实现**复制到输出目录**属性为 true 的文件。 每次生成项目，或按 F5，将文件复制到 bin 文件夹，并对该文件中，不是指向你的项目的根文件夹中文件的更改。 仅当使用编辑数据库架构或数据时更改项目根文件夹中的数据库文件**服务器资源管理器**，**数据库资源管理器**或其他工具窗口。  
  
 下表描述的设置**复制到输出目录**属性。  
  
|设置|行为|  
|-------------|--------------|  
|**如果较新则复制**（.sdf 文件的默认值）|数据库文件从项目目录复制到**bin** directory 第一次生成项目。 每次生成项目时，**修改日期**文件的属性进行比较。 如果项目文件夹中的文件较新，则将其复制到**bin**文件夹，替换当前存在的文件。 如果中的文件**bin**文件夹较新，不会复制文件。 此设置保持在运行时对数据进行任何更改，这意味着，每次运行应用程序并将更改保存到数据，这些更改才会显示在下次运行应用程序。 **注意：** 我们不建议使用此选项对于.mdb 或.mdf 文件。 即使在对数据不进行任何更改时，可以更改数据库文件。 只须打开数据文件中的连接 (例如，通过展开**表**中的节点**服务器资源管理器**) 可以将其标记为更高版本。|  
|**始终复制**（.mdf 和.mdb 文件的默认值）|每次生成应用程序时，数据库文件是从项目目录复制到 /bin 目录中。 因此，如果生成应用程序并将更改保存到 /bin 目录中的文件，这些更改会覆盖原始文件复制到 /bin 目录的下一个时间。|  
|**不复制**|该文件是永远不会复制或覆盖由项目系统。 您必须手动复制文件从项目目录到输出目录如果使用此设置。|  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-respond-to-the-local-database-file-dialog-box"></a>若要响应本地数据库文件对话框  
  
-   单击**是**如果想要 Visual Studio 将数据库文件复制到你的项目中并修改连接以指向你的项目中的副本。 有关如何使用你的项目中的数据库文件的详细信息，请参阅[本地数据概述](../data-tools/local-data-overview.md)。  
  
-   单击**否**如果不希望 Visual Studio 将数据库文件复制到你的项目。 相反，连接将指向原始位置中的文件和数据库文件将不作为文件添加到项目。  
  
## <a name="see-also"></a>请参阅  
 [演练： 连接到本地数据库文件 （Windows 窗体） 中的数据](../data-tools/walkthrough-connecting-to-data-in-a-local-database-file-windows-forms.md)   
 [连接到 Access 数据库中的数据（Windows 窗体）](../data-tools/connect-to-data-in-an-access-database-windows-forms.md)