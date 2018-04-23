---
title: 有关文件扩展名 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2c940319cd0ce3204f6dd9bb62e731de49b8baac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="about-file-name-extensions"></a>有关文件扩展名
当你注册 VSPackage 的文件扩展时，你将其与关联的版本[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。 这是重要如果多个是一份[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]的计算机上安装。  
  
 在使用指向关联的编程标识符 (ProgID) 的默认值的注册表项下注册 Vspackage 的文件扩展名。  
  
 下面是.vcproj 文件扩展名的注册信息的示例：  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 与关联的文件[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]必须具有已进行版本管理的 ProgID，如`VisualStudio.vcproj.8.0`，允许通过并行安装要维护产品版本间的文件扩展名关联的产品。 特定于版本的 ProgID 还可以使用标准谓词，如打开，编辑，并在其他方面，而无需考虑的覆盖或其他应用程序或的版本覆盖[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
 在某些情况下，不应更改与文件扩展名相关联的 ProgID。 例如，文件扩展名为.htm 的 ProgID (progid = htmlfile) 进行硬编码中的许多操作系统中的位置和是广泛已知和中使用关联.htm 和.html 文件。  
  
## <a name="see-also"></a>另请参阅  
 [注册-并排部署的文件扩展名](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [指定文件扩展名的文件处理程序](../extensibility/specifying-file-handlers-for-file-name-extensions.md)