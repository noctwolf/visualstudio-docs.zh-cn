---
title: 如何： 设置 Office 解决方案的配置信息
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87f50856439158d6d931b519fb35e98970ef7d58
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670309"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>如何： 设置 Office 解决方案的配置信息
  配置文件可用于配置特定于在 Office 解决方案的设置。 可以指定程序集绑定策略、 远程处理对象、 调试和跟踪设置等设置。  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>若要将配置文件添加到你的 Office 项目  
  
1.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
2.  在中**类别**窗格中，单击**常规**。  
  
3.  在中**模板**窗格中，选择**应用程序配置文件**。  
  
4.  在中**名称**框中，键入相同的名称为程序集并加上扩展名 *.config*。例如，Excel 项目程序集的配置文件称为*ExcelWorkbook1.dll*将被命名为*ExcelWorkbook1.dll.config*。  
  
5.  单击 **添加**。  
  
6.  创建配置文件根据应用程序配置文件架构。 有关详细信息，请参阅[的.NET Framework 配置文件架构](/dotnet/framework/configure-apps/file-schema/index)。  
  
 有使用 Office 项目的配置文件没有特殊的注意事项。  
  
## <a name="see-also"></a>请参阅  
 [.NET Framework 的配置文件架构](/dotnet/framework/configure-apps/file-schema/index)   
 [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)   
 [部署 Office 解决方案](../vsto/deploying-an-office-solution.md)  
  
  