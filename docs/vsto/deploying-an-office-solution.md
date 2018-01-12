---
title: "部署 Office 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office applications [Office development in Visual Studio], deploying Office solutions
- Office development in Visual Studio, deploying Office solutions
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- deploying applications [Office development in Visual Studio], Office solutions (2007 system)
- Office development in Visual Studio, troubleshooting
- Office development in Visual Studio, event viewer
- ClickOnce deployment [Office development in Visual Studio], about ClickOnce solution deployments
- Office solutions [Office development in Visual Studio], deploying
- deploying applications [Office development in Visual Studio], troubleshooting
- solutions [Office development in Visual Studio], deploying Office solutions (2007 system)
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4cb4c4b2e5154293279e0993daabdbc8f74165b3
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="deploying-an-office-solution"></a>部署 Office 解决方案
  可以使用 ClickOnce 或 Windows Installer 来部署 Office 解决方案。 通过使用 ClickOnce，可以减少部署和更新解决方案所需的步骤数。 如果使用 Windows Installer，可以控制解决方案的安装方式，以及在用户安装解决方案时，安装程序显示的页。  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有内存占用较小与 VSTO 外接程序和解决方案，相比，并且你可以通过使用几乎任何 web 编程技术，例如 HTML5、 JavaScript、 CSS3 和 XML 生成它们。  
  
## <a name="deploying-a-solution-by-using-clickonce"></a>使用 ClickOnce 部署解决方案  
 使用 ClickOnce 部署解决方案时，可将其发布到一个中心位置，用户能够从中安装并运行解决方案。 可以更新解决方案，而无需将新的安装程序分发给用户。  此部署选项更简单，但无法显示用户自定义安装页。 此外，必须在包含多个用户的任何计算机上多次安装解决方案。 请参阅[使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)。  
  
## <a name="deploying-a-solution-by-using-windows-installer"></a>使用 Windows Installer 部署解决方案  
 使用 Windows Installer 部署解决方案时，可将安装程序分发给用户，用户将使用此程序安装解决方案。 安装程序可以同时为一台计算机上的所有用户安装解决方案，而非仅当前用户。 还可以更好地控制在用户安装解决方案时显示给用户的选项。 例如，可以显示许可协议或者使用户安装解决方案的特定组件。 不过，如果更新解决方案，必须分发一个新的安装程序。 请参阅[使用 Windows Installer 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-windows-installer.md)。  
  
## <a name="see-also"></a>请参阅  
 [保护 Office 解决方案](../vsto/securing-office-solutions.md)   
 [通过使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [使用 Windows Installer 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-windows-installer.md)   
 [Office 解决方案部署疑难解答](../vsto/troubleshooting-office-solution-deployment.md)  
  
  