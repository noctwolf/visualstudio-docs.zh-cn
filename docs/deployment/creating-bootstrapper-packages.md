---
title: 创建引导程序包
ms.custom: ''
ms.date: 05/02/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], prerequisites
- deploying applications [Visual Studio], custom prerequisites
- prerequisites, custom
- RedistList file
- custom prerequisites
- redistributables list
ms.assetid: ba1a785b-693d-446b-bcae-b88cadee73d1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d3cc80a6ca29583fdc445b507aeb8f87267459d8
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572720"
---
# <a name="create-bootstrapper-packages"></a>创建引导程序包
安装程序是可配置为检测并安装可再发行组件（如 Windows Installer (.msi) 文件和可执行程序）的一般安装程序。 安装程序也称为“引导程序”。 它通过一组 XML 清单进行编程，这些清单指定用于管理组件安装的元数据。  每个可再发行组件或先决条件中，出现在**先决条件**ClickOnce 的对话框中是一个引导程序包。 一个引导程序包是一组目录和文件，其中包含用于说明系统必备组件的安装方式的清单文件。 
  
引导程序首先检测是否已安装所有系统必备组件。 如果未安装系统必备组件，引导程序将首先显示相关许可协议。 接着，在最终用户接受许可协议后，将开始安装相应的系统必备组件。 否则，如果检测到所有的系统必备组件，引导程序将直接启动应用程序的安装程序。  
  
## <a name="create-custom-bootstrapper-packages"></a>创建自定义引导程序包  
可以通过使用 Visual Studio 中的 XML 编辑器来生成引导程序清单。 若要查看创建引导程序包的示例，请参阅[演练： 创建自定义引导程序隐私提示](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md)。  
  
若要创建引导程序包，你必须创建产品清单和，每个本地化的组件，以及一个包清单的版本。
  
* 产品清单*product.xml*，包含程序包的任何非特定于语言的元数据。 它包含可再发行组件的所有本地化版本通用的元数据。  若要创建此文件，请参阅[如何： 创建产品清单](../deployment/how-to-create-a-product-manifest.md)。
  
* 包清单*package.xml*，包含特定于语言的元数据; 它通常包含本地化的错误消息。 必须至少为组件的每个本地化版本提供一个程序包清单。 若要创建此文件，请参阅[如何： 创建程序包清单](../deployment/how-to-create-a-package-manifest.md)。
  
在创建这两个文件之后，请将产品清单文件放置在一个依据自定义引导程序命名的文件夹中。 程序包清单文件将放置到一个依据区域设置命名的文件夹中。 例如，如果程序包清单文件针对的是英语版的再发行程序，请将该文件放置在一个名为 en 的文件夹中。 对于每个区域设置（如 ja 代表日语，de 代表德语）重复此过程。 最终的自定义引导程序包的文件夹结构将如下所示。  

    ```
    CustomBootstrapperPackage
      product.xml
      CustomBootstrapper.msi
      de
        eula.rtf
        package.xml
      en
        eula.rtf
        package.xml
      ja
        eula.rtf
        package.xml
    ```
  
接下来，将可再发行文件复制到引导程序文件夹位置。 有关详细信息，请参阅 [How to: Create a Localized Bootstrapper Package](../deployment/how-to-create-a-localized-bootstrapper-package.md)。
 
    *\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
    
或  
    
    *\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
  
也可以根据以下注册表项中的 **“Path”** 值确定引导程序文件夹位置：  
  
    *HKLM\Software\Microsoft\GenericBootstrapper\11.0*
  
在 64 位系统上使用以下注册表项：  
  
    *HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper\11.0*
  
每个可再发行组件均位于程序包目录下它们自己的子文件夹中。 产品清单和可再发行文件必须可将放入此子文件夹。 必须根据区域性名称命名的子文件夹中放置组件和包清单的本地化的版本。  
  
这些文件复制到引导程序文件夹中之后，相应的引导程序包自动出现在 Visual Studio**先决条件**对话框。 如果你的自定义引导程序包未显示，关闭并重新打开**先决条件**对话框。 有关详细信息，请参阅 [“系统必备”对话框](../ide/reference/prerequisites-dialog-box.md)。  
  
下表显示由引导程序自动填充的属性。  
  
|属性|描述|  
|--------------|-----------------|  
|ApplicationName|应用程序的名称。|  
|ProcessorArchitecture|可执行文件的目标平台的处理器和每字位数。 包括以下值：<br /><br /> -Intel<br />-IA64<br />AMD64|  
|[Version9x](https://msdn.microsoft.com/en-us/library/aa372490\(v=vs.140\).aspx)|Microsoft Windows 95、Windows 98 或 Windows ME 操作系统的版本号。 版本的语法是 Major.Minor.ServicePack。|  
|[自](https://msdn.microsoft.com/en-us/library/aa372495\(v=vs.140\).aspx)|Windows NT、Windows 2000、Windows XP、Windows Vista、Windows Server 2008 或 Windows 7 操作系统的版本号。 版本的语法是 Major.Minor.ServicePack。|  
|[VersionMSI](https://msdn.microsoft.com/en-us/library/aa372493\(v=vs.140\).aspx)|安装期间运行的 Windows Installer 程序集 (msi.dll) 的版本。|  
|[AdminUser](https://msdn.microsoft.com/en-us/library/aa367545\(v=vs.140\).aspx)|如果用户具有管理员特权，则设置此属性。 值为 true 或 false。|  
|InstallMode|安装模式指示需要安装组件的位置。 包括以下值：<br /><br /> 从供应商的网站安装-HomeSite-先决条件。<br />从你选择的位置安装-SpecificSite-先决条件。<br />从与应用程序相同的位置安装-SameSite-先决条件。|  
  
## <a name="separating-redistributables-from-application-installations"></a>使可再发行文件与应用程序安装分离  
你可以阻止在安装项目中部署可再发行文件。 为此，请在 .NET Framework 目录的 RedistList 文件夹中创建一个可再发行文件列表：  
  
`%ProgramFiles%\Microsoft.NET\RedistList`  
  
可再发行文件列表是一个 XML 文件，你应采用下面的格式命名该文件： *公司名称*.*组件名称*.RedistList.xml。 因此，例如，如果组件名为 Datawidgets 且由 acme 开发，使用*Acme.DataWidgets.RedistList.xml*。 可再发行文件列表的内容的示例可能像下面这样：  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<FileList Redist="Acme.DataWidgets" >  
<File AssemblyName="Acme.DataGrid" Version="1.0.0.0" PublicKeyToken="b03f5f7f11d50a3a" Culture="neutral" ProcessorArchitecture="MSIL" InGAC="true" />  
</FileList>  
```  
  
## <a name="see-also"></a>请参阅  
 [如何：与 ClickOnce 应用程序一起安装必备组件](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [系统必备组件对话框](../ide/reference/prerequisites-dialog-box.md)   
 [产品和程序包架构引用](../deployment/product-and-package-schema-reference.md)   
 [使用 Visual Studio 2005 引导程序开始你的安装](http://go.microsoft.com/fwlink/?LinkId=107537)
