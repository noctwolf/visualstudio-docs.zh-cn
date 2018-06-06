---
title: 使用 Office 解决方案概述中的本地数据库文件
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 01e9dc3df93e1f721eba9ce3bcf65d4fb8bb1ca1
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767577"
---
# <a name="use-local-database-files-in-office-solutions-overview"></a>使用 Office 解决方案概述中的本地数据库文件
  你可以包括数据库文件，如 SQL Server Express (*.mdf*) 文件或 Microsoft Office Access (*.mdb*) 文件，请在 Office 解决方案。 这使最终用户能够在其中维护中央的数据库不是必需的例如在使用仅一台计算机的本地清单解决方案的情况下对本地数据库进行维护。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="import-the-database-file-into-a-project"></a>导入的项目的数据库文件  
 若要将数据库文件导入你的项目，使用**数据源配置向导**创建数据源基于的数据库文件。 向导将数据库文件和一个类型化数据集添加到你的项目。  
  
## <a name="deploy-the-database-file"></a>部署数据库文件  
 **数据源配置向导**使用相对路径来创建连接到本地数据库文件。 这使您可以将解决方案从一台计算机复制到另一个，如果维护文件的相对位置。  
  
 如果你将你的解决方案部署到服务器，然后将分发到每个最终用户的文档，必须手动分发数据库文件，并将其安装在同一位置相对于文档。 这意味着，最终用户不能将文档移到新位置他或她在计算机上，除非他或她也会移动数据库文件。  
  
## <a name="local-database-files-and-caching-the-dataset"></a>本地数据库文件和缓存数据集  
 在 Microsoft Office Excel 和 Microsoft Office Word 文档级解决方案中，你可以通过将标记该特性的数据集实例中缓存文档中的数据集<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>。 当你将数据库文件添加到你的项目使用**数据源配置向导**，类型化数据集自动添加到你的项目。 很少需要应用<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>到此数据集，因为已存在用户的计算机上本地数据。 有关详细信息，请参阅[缓存数据](../vsto/caching-data.md)。  
  
## <a name="see-also"></a>请参阅  
 [将数据绑定到 Office 解决方案中的控件](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [如何： 用数据库中的数据填充文档](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [如何： 使用主机控件中的数据更新数据源](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [部署 Office 解决方案](../vsto/deploying-an-office-solution.md)   
 [缓存数据](../vsto/caching-data.md)  
  
  