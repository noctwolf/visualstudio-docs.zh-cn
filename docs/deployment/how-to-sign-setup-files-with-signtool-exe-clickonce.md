---
title: 如何： 安装与 SignTool.exe (ClickOnce) 文件进行签名 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, signtool.exe
- deploying applications [ClickOnce], re-signing setup.exe
- ClickOnce deployment, signtool.exe
- ClickOnce applications, re-signing setup.exe
- ClickOnce deployment, re-signing setup.exe
ms.assetid: 545a4005-d283-4110-9821-c78a9833c250
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b66d9440ebcf62c59049b45769a2244fc773480e
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081496"
---
# <a name="how-to-sign-setup-files-with-signtoolexe-clickonce"></a>如何： 安装与 SignTool.exe (ClickOnce) 文件进行签名
可以使用*SignTool.exe*若要为安装程序 (*setup.exe*)。 此过程有助于确保不会在最终用户计算机上安装经过篡改的文件。  
  
 默认情况下，ClickOnce 具有签名的清单和一个签名的安装程序。 但是，如果想在以后更改安装程序的参数，则以后必须对该安装程序进行签名。 如果对安装程序签名后更改参数，则签名将会损坏。  
  
 下面的过程将生成未签名的清单和未签名的安装程序。 然后，在 Visual Studio 中启用 ClickOnce 签名以生成签名的清单。 此安装程序将处于未签名状态，以便客户可以用他们自己的证书对可执行文件进行签名。  
  
### <a name="to-generate-an-unsigned-setup-program-and-sign-later"></a>生成未签名的安装程序并在以后进行签名  
  
1.  在开发计算机上，安装想要用于对清单进行签名的证书。  
  
2.  选择中的项目**解决方案资源管理器**。  
  
3.  上**项目**菜单上，单击*ProjectName* **属性**。  
  
4.  在中**签名**页上，清除**ClickOnce 清单签名**。  
  
5.  在中**发布**页上，单击**先决条件**。  
  
6.  验证所有系统必备组件未选择，然后单击**确定**。  
  
7.  在中**发布**页上，验证的发布设置，然后单击**立即发布**。  
  
     该解决方案会将未签名的应用程序清单、未签名的部署清单、特定于版本的文件以及未签名的安装程序发布到发布文件夹位置。  
  
8.  在中**发布**页上，单击**先决条件**。  
  
9. 在中**先决条件**对话框中，清除**创建用于安装系统必备组件安装程序**。  
  
10. 在中**发布**页上，验证的发布设置，然后单击**立即发布**。  
  
     该解决方案会将签名的应用程序清单、签名的部署清单和特定于版本的文件发布到发布文件夹位置。 发布过程不会覆盖未签名的安装程序。  
  
11. 在客户站点，打开命令提示符。  
  
12. 将更改为包含的目录 *.exe*文件。  
  
13. 登录 *.exe*文件使用以下命令：  
  
    ```cmd  
    signtool sign /sha1 CertificateHash Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
     例如，若要为安装程序签名，请使用下列命令之一：  
  
    ```cmd  
    signtool sign /sha1 CCB... Setup.exe  
    signtool sign /f CertFileName Setup.exe  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何： 对应用程序和部署清单重新签名](../deployment/how-to-re-sign-application-and-deployment-manifests.md)
