---
title: 为 Windows Installer 部署准备扩展 |Microsoft 文档
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
ms.openlocfilehash: ef51b3cb0f84a470f104ff688c1149e607d16f71
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="preparing-extensions-for-windows-installer-deployment"></a>准备 Windows Installer 部署扩展
Windows Installer 包 (MSI) 不能用于部署 VSIX 包。 但是，你可以提取 MSI 部署 VSIX 包的内容。 本文档说明如何准备其默认输出是包含在安装项目的 VSIX 包的项目。  
  
## <a name="preparing-an-extension-project-for-windows-installer-deployment"></a>为 Windows Installer 部署准备一个扩展项目  
 添加到安装项目之前，请在新的扩展项目中执行这些步骤。  
  
#### <a name="to-prepare-an-extension-project-for-windows-installer-deployment"></a>若要为 Windows Installer 部署准备一个扩展项目  
  
1.  创建 VSPackage、 MEF 组件、 编辑器修饰或包括 VSIX 清单其他扩展性项目类型。  
  
2.  在代码编辑器中打开的 VSIX 清单。  
  
3.  设置 VSIX 清单到 InstalledByMsi 元素`true`。 有关 VSIX 清单的详细信息，请参阅[VSIX 扩展架构 2.0 引用](../extensibility/vsix-extension-schema-2-0-reference.md)。  
  
     这可以阻止 VSIX 安装程序尝试安装该组件。  
  
4.  右键单击中的项目**解决方案资源管理器**单击**属性**。  
  
5.  选择**VSIX**选项卡。  
  
6.  选中的复选框标记为**到以下位置的副本 VSIX 内容**键入到安装项目会选取这些文件的路径。  
  
## <a name="extracting-files-from-an-existing-vsix-package"></a>从现有的 VSIX 包中提取文件  
 执行这些步骤以将现有的 VSIX 包的内容添加到安装项目，如果你没有源代码文件。  
  
#### <a name="to-extract-files-from-an-existing-vsix-package"></a>若要从现有的 VSIX 包中提取文件  
  
1.  重命名。包含中的扩展的 VSIX 文件*filename*到.vsix *filename*.zip。  
  
2.  将.zip 文件的内容复制到一个目录。  
  
3.  从目录中删除 [Content_types].xml 文件。  
  
4.  编辑 VSIX 清单中，如前面的过程中所示。  
  
5.  将剩余的文件添加到你的安装项目。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Studio 安装程序部署](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [演练： 创建自定义操作](http://msdn.microsoft.com/en-us/4bd4b63a-2b91-431e-839c-5752443f0eaf)