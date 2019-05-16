---
title: 在文档级解决方案中的文档保护
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- restricted permissions [Office development in Visual Studio]
- permissions [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- Office documents [Office development in Visual Studio], restricted permissions
- documents [Office development in Visual Studio], restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b6cc01c6506c4a3fca85029a8dcaf08607427ea4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62956200"
---
# <a name="document-protection-in-document-level-solutions"></a>在文档级解决方案中的文档保护
  可以使用 Microsoft Office Word 和 Microsoft Office Excel 文档级项目中的保护的功能。 这些功能可以阻止未经授权的用户对受保护文档各部分进行更改。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 使用 Excel，你可以启用保护打开和关闭设计器中打开该工作簿时发生。 使用 Word，可以启用保护仅在设计器之外。 在运行时，可以启用或禁用保护，以编程方式为 Word 和 Excel。

 在设计器中打开的文档上启用文档保护后，所有控件都将都从中**工具箱**进行不可用，或不能将任何内容，从**数据源**对文档的窗口。

## <a name="serverdocument-and-protected-documents"></a>ServerDocument 和受保护的文档
 如果保护文档，则数据缓存不能从外部文档进行访问。 不能使用<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>类来检索或处理数据缓存在受保护的文档，或使用其他方法的<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument>类。

## <a name="word-document-protection-in-the-designer"></a>在设计器中的 Word 文档保护
 如果在 Visual Studio 中打开时，可添加到 Word 文档或模板保护，不能启动强制在设计器中的保护。 文档是在设计模式下，虽然它在 Visual Studio 中打开，且它之前，必须在运行模式可以开始实施保护。

 但是，如果创建使用启用了保护的现有 Word 文档的项目，在设计器中打开时保护此文档。 不能编辑受保护的文档，部分，但您仍然可以编写代码在代码编辑器中自动执行该文档。 在 Visual Studio 中打开文档时启用保护，也不能生成项目。

 在文档处于设计器中打开，以便可以编辑该文档并生成项目时，你可以关闭保护。 在进行调试; 时不能将关闭设计器中复制的保护在调试期间打开的文档是从设计器中打开的单独副本 (输出副本存储在 *\bin* 目录的 Visual Basic 中，并 *\bin\debug* 目录C#).

 可以启用在副本上的文档的设计器中打开通过关闭 Visual Studio 中的项目中，打开位于项目目录中的文档的副本并开启保护的保护。

## <a name="enforce-word-document-protection-on-build"></a>强制在生成的 Word 文档保护
 Visual Studio 将启动强制在生成过程中，为 Word 文档和模板保护，以便文档打开以进行调试时启用保护。 使用空密码保护此文档。

 保护是在过程中启用生成因此，如果在文档中的代码<xref:Microsoft.Office.Tools.Word.Document.Startup>可能会导致异常或更改应用程序的行为的事件，此代码可以正确调试。 如果启用保护后打开文档时，不能调试或测试初始化代码。

## <a name="setting-the-password"></a>设置密码
 Visual Studio 会自动启用保护，但默认情况下提供没有密码。 如果你想拥有密码的文档保护，必须将其添加，然后再部署你的解决方案。 添加密码，可允许授权的用户从文档中; 删除保护如果没有密码，不能轻松地删除保护。 有关设置密码的详细信息，请参阅特定 Office 应用程序中的帮助。

## <a name="see-also"></a>请参阅
- [如何：以编程方式保护文档和文档的某些部分](../vsto/how-to-programmatically-protect-documents-and-parts-of-documents.md)
- [Office 开发示例和演练](../vsto/office-development-samples-and-walkthroughs.md)
- [信息权限管理和托管的代码扩展概述](../vsto/information-rights-management-and-managed-code-extensions-overview.md)
- [Office 文档上的密码保护](../vsto/password-protection-on-office-documents.md)
- [如何：允许代码以使用受限权限的文档的后台运行](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)
- [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)
