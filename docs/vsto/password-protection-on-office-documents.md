---
title: Office 文档上的密码保护 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- passwords [Office development in Visual Studio], document protections
- documents [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio, restricted permissions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5d85f1dc0aa54da22b02259aea372f2ad6dd42ac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="password-protection-on-office-documents"></a>Office 文档的密码保护
  很可能你的 Microsoft Office Word 文档和 Microsoft Office Excel 工作簿上设置密码，以便它们不能打开的人不知道的密码。 此选项称为**处于打开状态的密码**。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 你可以创建文档级项目中使用现有的文档和工作簿具有**处于打开状态的密码**启用。 Visual Studio 中的行为是不同的 Word 和 Excel 的文档具有**处于打开状态的密码**启用。  
  
 有关启用信息**处于打开状态的密码**，请参阅在 Word 或 Excel 中的帮助。  
  
## <a name="behavior-of-excel-and-word"></a>Excel 和 Word 的行为  
 每次在 Visual Studio 中具有打开的 Excel 工作簿**处于打开状态的密码**启用，Excel 将提示你输入密码。 生成你的解决方案时你将会再次提示输入的密码，因为在生成期间打开该文档。  
  
 第一次你打开 Word 文档在 Visual Studio 中具有**处于打开状态的密码**启用，Word 将提示你输入密码。 成功输入密码之后,**处于打开状态的密码**从文档中移除并打开该文档将不再要求输入密码。 如果您要在你的解决方案中的文档要需要密码才能它可以打开，则必须启用**处于打开状态的密码**最终生成之后且在部署解决方案之前。  
  
## <a name="see-also"></a>请参阅  
 [在文档级解决方案中的文档保护](../vsto/document-protection-in-document-level-solutions.md)   
 [信息权限管理与托管的代码扩展概述](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [如何： 允许代码使用受限权限的文档的后台运行](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)  
  
  