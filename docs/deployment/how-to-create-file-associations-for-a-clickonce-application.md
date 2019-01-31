---
title: 如何：创建 ClickOnce 应用程序的文件关联 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- file associations, ClickOnce applications
- ClickOnce deployment, file associations
ms.assetid: 835230c8-3177-440f-85e3-e40f1d8b4f9d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f311705a6cb898ee9bff81a3bbad3890aea92c7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54947304"
---
# <a name="how-to-create-file-associations-for-a-clickonce-application"></a>如何：创建 ClickOnce 应用程序的文件关联
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 这样，当用户打开这些类型的文件将自动启动该应用程序，应用程序可以与一个或多个文件扩展名相关联。 添加到的文件名称扩展支持[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序非常简单。  
  
### <a name="to-create-file-associations-for-a-clickonce-application"></a>若要创建 ClickOnce 应用程序的文件关联  
  
1. 创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序通常情况下，或使用现有[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序。  
  
2. 使用文本或 XML 编辑器，如记事本中打开应用程序清单。  
  
3. 查找 `assembly` 元素。 有关详细信息，请参阅 [ClickOnce 应用程序清单](../deployment/clickonce-application-manifest.md)。  
  
4. 为的子`assembly`元素中，添加`fileAssociation`元素。 `fileAssociation`元素具有四个属性：  
  
   - `extension`：你想要将应用程序与关联文件扩展名。  
  
   - `description`：文件类型，不会在 Windows shell 中的说明。  
  
   - `progid`：唯一地标识要将其标记在注册表中的文件类型的字符串。  
  
   - `defaultIcon`：若要使用此文件类型图标。 必须为应用程序清单中的文件资源添加图标。 有关详细信息，请参阅[如何：将数据文件添加到 ClickOnce 应用程序中](../deployment/how-to-include-a-data-file-in-a-clickonce-application.md)。  
  
     有关的示例`file`并`fileAssociation`元素，请参阅[ \<fileAssociation > 元素](../deployment/fileassociation-element-clickonce-application.md)。  
  
5. 如果你想要将多个文件类型与应用程序相关联，将添加其他`fileAssociation`元素。 请注意，`progid`属性应为每个不同。  
  
6. 完成应用程序清单后，重新对清单进行签名。 您可以使用执行此操作从命令行*Mage.exe*。  
  
    `mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx`  
  
    有关详细信息，请参阅 [Mage.exe（清单生成和编辑工具）](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)  
  
## <a name="see-also"></a>请参阅  
 [\<fileAssociation > 元素](../deployment/fileassociation-element-clickonce-application.md)   
 [ClickOnce 应用程序清单](../deployment/clickonce-application-manifest.md)   
 [Mage.exe（清单生成和编辑工具）](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)