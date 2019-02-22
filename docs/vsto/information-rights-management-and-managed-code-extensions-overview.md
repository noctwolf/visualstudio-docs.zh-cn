---
title: 信息权限管理和托管的代码扩展概述
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 109f6b85653a842f7c6fc9ce2d2c09b74113bbc7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641242"
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>信息权限管理和托管的代码扩展概述
  Microsoft Office Word 和 Microsoft Office Excel 提供了信息权限管理 (IRM) 功能，可以帮助您防止未经授权的人员查看或更改的敏感信息。 有关信息权限管理的工作原理的详细信息，请参阅特定 Office 应用程序中的帮助。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="run-code-behind-documents-with-restricted-permissions"></a>使用受限权限运行的文档的后台代码
 如果解决方案包含文档或工作簿使用 IRM，默认情况下，Word 和 Excel 不允许运行任何代码。 如果您是文档的作者，或具有完全控制访问权限，可以更改默认值，以便你的解决方案能起作用。 有关详细信息，请参阅[如何：允许代码以使用受限权限运行的文档的后台](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)。

 IRM 可防止使用<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument>检索或处理缓存到文档中的数据。

## <a name="end-users-to-restrict-permissions-to-documents-that-use-managed-code-extensions"></a>最终用户能够将权限限制给使用托管的代码扩展的文档
 你的解决方案中具有完全控制访问权限的文档或工作簿的任何人可以使用 IRM 限制的权限。 例如，如果会计部门中的最终用户将使用自动填充数据库中的数据的工作表的解决方案，该用户可能想要允许只向他或她部门中的人员更改访问权限和对其他人读取访问权限。 当用户添加受限的权限时，默认情况下，无法运行代码隐藏工作表，并不会使用数据填充工作表。

 若要解决此问题，具有完全控制访问权限的文档或工作簿的人员必须更改默认权限设置为允许以编程方式访问的对象模型。 有关详细信息，请参阅[如何：允许代码以使用受限权限运行的文档的后台](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)。

## <a name="see-also"></a>请参阅
- [在文档级解决方案中的文档保护](../vsto/document-protection-in-document-level-solutions.md)
- [Office 文档上的密码保护](../vsto/password-protection-on-office-documents.md)
- [保护 Office 解决方案](../vsto/securing-office-solutions.md)
- [部署 Office 解决方案](../vsto/deploying-an-office-solution.md)
- [设计和创建 Office 解决方案](../vsto/designing-and-creating-office-solutions.md)
