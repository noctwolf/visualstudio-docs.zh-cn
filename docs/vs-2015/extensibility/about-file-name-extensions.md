---
title: 有关文件扩展名 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b8a299d7b2470b16761e4a418e0717a91c2929e9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483667"
---
# <a name="about-file-name-extensions"></a>关于文件扩展名
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[文件扩展名有关](https://docs.microsoft.com/visualstudio/extensibility/about-file-name-extensions)。  
  
当你注册 VSPackage 的文件扩展名时，您将其与关联的版本[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 这是重要如果多个是的一个版本[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]的计算机上安装。  
  
 在 HKEY_CLASSES_ROOT 项默认值指向关联的编程标识符 (ProgID) 下注册 Vspackage 的文件扩展名。  
  
 以下是.vcproj 文件扩展名的注册信息的示例：  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 与关联的文件[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]必须具有版本控制的 ProgID，如`VisualStudio.vcproj.8.0`，以允许通过并行安装要维护产品版本间的文件扩展名关联的产品。 特定于版本的 ProgID 还可以使用标准动词，如打开、 编辑和在其他方面，而无需考虑的覆盖或其他应用程序或版本的覆盖[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。  
  
 在某些情况下，不应更改与文件扩展名相关联的 ProgID。 例如，文件扩展名为.htm 的 ProgID (progid = htmlfile) 被硬编码中的许多操作系统中的位置和是广泛已知和已用中与.htm 和.html 文件的关联。  
  
## <a name="see-also"></a>请参阅  
 [通过并行部署注册文件扩展名](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [指定文件扩展名的文件处理程序](../extensibility/specifying-file-handlers-for-file-name-extensions.md)

