---
title: Office 文档上的密码保护
ms.date: 02/02/2017
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
ms.openlocfilehash: 4603a6f5722279ccdaf057d30d3bc6e911c4c47e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53856996"
---
# <a name="password-protection-on-office-documents"></a>Office 文档上的密码保护
  就可以在 Microsoft Office Word 文档和 Microsoft Office Excel 工作簿上设置密码，以便它们不能打开的人不知道密码。 此选项将称为**处于打开状态的密码**。  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 可以创建文档级项目中使用现有的文档和工作簿具有**处于打开状态的密码**启用。 在 Visual Studio 中的行为是不同的 Word 和 Excel 文档，具有**处于打开状态的密码**启用。  
  
 有关启用信息**处于打开状态的密码**，请参阅在 Word 或 Excel 的帮助。  
  
## <a name="behavior-of-excel-and-word"></a>Excel 和 Word 的行为  
 每次在 Visual Studio 中具有打开的 Excel 工作簿**处于打开状态的密码**启用，Excel 会提示你输入密码。 生成解决方案时，将会再次提示输入密码，因为在生成期间打开文档。  
  
 第一次您打开一个 Word 文档在 Visual Studio 中具有**处于打开状态的密码**启用，Word 会提示您输入密码。 成功输入密码之后,**处于打开状态的密码**从文档中删除并打开该文档将不再要求输入密码。 如果想要在文档中你的解决方案需要密码，然后它可以打开，则必须启用**处于打开状态的密码**最终生成和部署解决方案之前。  
  
## <a name="see-also"></a>请参阅  
 [在文档级解决方案中的文档保护](../vsto/document-protection-in-document-level-solutions.md)   
 [信息权限管理和托管的代码扩展概述](../vsto/information-rights-management-and-managed-code-extensions-overview.md)   
 [如何：允许代码以使用受限权限的文档的后台运行](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)   
 [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)  
