---
title: 为 Windows 安装程序部署准备扩展 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix msi
ms.assetid: 5ee2d1ba-478a-4cb7-898f-c3b4b2ee834e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ef69ac45a090aa4395aa15d1395cff1665255b51
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639108"
---
# <a name="prepare-extensions-for-windows-installer-deployment"></a>准备 Windows 安装程序部署扩展
Windows Installer 程序包 (MSI) 不能用于部署 VSIX 包。 但是，您可以提取 MSI 部署 VSIX 包的内容。 本文档演示如何进行准备，其默认输出是包含在安装程序项目中的 VSIX 包的项目。  
  
## <a name="prepare-an-extension-project-for-windows-installer-deployment"></a>为 Windows 安装程序部署准备扩展项目  
 将添加到安装项目之前在新的扩展项目上执行这些步骤。  
  
### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>若要为 Windows 安装程序部署准备扩展项目  
  
1.  创建 VSPackage，MEF 组件、 编辑器修饰或其他包含 VSIX 清单的可扩展性项目类型。  
  
2.  在代码编辑器中打开 VSIX 清单。  
  
3.  设置`InstalledByMsi`到 VSIX 清单元素`true`。 有关 VSIX 清单的详细信息，请参阅[VSIX 扩展架构 2.0 参考](../extensibility/vsix-extension-schema-2-0-reference.md)。  
  
     这可以防止 VSIX 安装程序尝试安装该组件。  
  
4.  右键单击该项目中的**解决方案资源管理器**然后单击**属性**。  
  
5.  选择**VSIX**选项卡。  
  
6.  选中复选框标记为**到以下位置复制 VSIX 内容**键入到安装项目会选取这些文件的路径。  
  
## <a name="extract-files-from-an-existing-vsix-package"></a>从现有的 VSIX 包中提取文件  
 执行这些步骤将现有的 VSIX 包的内容添加到安装项目，您没有所需的源文件。  
  
### <a name="to-extract-files-from-an-existing-vsix-package"></a>若要从现有的 VSIX 包中提取文件  
  
1.  重命名 *。VSIX*文件包含从扩展*filename.vsix*到*filename.zip*。  
  
2.  将复制的内容 *.zip*到目录的文件。  
  
3.  删除 *[Content_types].xml*从目录的文件。  
  
4.  编辑 VSIX 清单中，如前面的过程中所示。  
  
5.  将剩余的文件添加到你的安装程序项目。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 安装程序部署](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [演练： 创建自定义操作](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)