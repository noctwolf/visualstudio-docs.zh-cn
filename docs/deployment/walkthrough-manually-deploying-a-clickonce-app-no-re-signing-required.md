---
title: 演练： 手动部署 ClickOnce 应用程序，不需要重新签名并且保留署名信息 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0584aac376345bc508e5f2088decd45b8c64783b
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>演练：手动部署不需要重新签名并且保留署名信息的 ClickOnce 应用程序
当你创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序并将它提供给客户进行发布和部署信息，客户通常必须更新部署清单并对它进行重新签名。 .NET Framework 3.5 时，仍在大多数情况下的首选的方法，使您能够创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]可以由其客户部署而无需重新生成新的部署清单的部署。 有关详细信息，请参阅[部署 ClickOnce 应用程序对于测试和生产服务器，而无需 Resigning](../deployment/deploying-clickonce-applications-for-testing-and-production-without-resigning.md)。  
  
 当你创建[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序，然后为其提供给客户进行发布和部署、 应用程序可以使用客户的品牌，也可以保留你的品牌。 例如，如果应用程序是一个单一的专有应用程序，你可能想要保留你的品牌。 如果应用程序高度自定义每个客户，你可能想要使用客户的品牌。 当你向组织要部署应用程序，.NET Framework 3.5，您可以保留你的品牌、 发布服务器信息以及安全签名。 有关详细信息，请参阅[创建 ClickOnce 应用程序的其他部署](../deployment/creating-clickonce-applications-for-others-to-deploy.md)。  
  
> [!NOTE]
>  在本演练中你部署的手动创建使用命令行工具 Mage.exe 或图形工具 MageUI.exe。 有关手动部署的详细信息，请参阅[演练： 手动部署 ClickOnce 应用程序](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)。  
  
## <a name="prerequisites"></a>系统必备  
 若要执行本演练中的步骤需要满足以下要求：  
  
-   你就可以部署一个 Windows 窗体应用程序。 此应用程序称为 WindowsFormsApp1。  
  
-   Visual Studio 或 Windows SDK。  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>若要部署 ClickOnce 应用程序具有多个部署和使用 Mage.exe 的品牌支持  
  
1.  打开 Visual Studio 命令提示符或[!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]命令提示符，并将更改为在其中将存储目录你[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]文件。  
  
2.  创建名为你的部署的当前版本的目录。 如果这是首次部署应用程序，则可以选择**1.0.0.0**。  
  
    > [!NOTE]
    >  你的部署的版本可能不同于你的应用程序文件的版本。  
  
3.  创建名为的子目录**bin** ，将所有应用程序文件，包括可执行文件、 程序集、 资源和数据文件复制。  
  
4.  生成使用 Mage.exe 调用应用程序清单。  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  对应用程序清单使用数字证书进行签名。  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  生成部署清单，mage.exe 的调用。 默认情况下，Mage.exe 会将标记你[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]作为安装应用程序，以便它可以同时在线运行和脱机状态的部署。 若要使应用程序可用，仅当用户处于联机状态时，使用`-i`自变量的值与`f`。 由于此应用程序将充分利用多个部署功能，排除`-providerUrl`mage.exe 的自变量。 (不包括的.NET framework 3.5 版中之前, 的版本中`-providerUrl`脱机应用程序会导致错误。)  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  不要对部署清单进行签名。  
  
8.  向的客户，将部署其网络上的应用程序中提供的所有文件。  
  
9. 此时，客户必须与自己自行生成的证书的部署清单签名。 例如，如果客户适用于名为 Adventure Works 的公司，他可以生成自签名的证书通过 MakeCert.exe 工具。 接下来，使用 Pvk2pfx.exe 工具组合到 PFX 文件，可传递给 Mage.exe 通过 MakeCert.exe 创建的文件。  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. 接下来，客户使用此证书部署清单进行签名。  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. 客户部署到其用户应用程序。  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>若要部署 ClickOnce 应用程序具有多个部署和使用 MageUI.exe 的品牌支持  
  
1.  打开 Visual Studio 命令提示符或[!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]命令提示符，并导航到目录，您将在其中存储你[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]文件。  
  
2.  创建名为的子目录**bin** ，将所有应用程序文件，包括可执行文件、 程序集、 资源和数据文件复制。  
  
3.  创建你的部署的当前版本命名的子目录。 如果这是首次部署应用程序，则可以选择**1.0.0.0**。  
  
    > [!NOTE]
    >  你的部署的版本可能不同于你的应用程序文件的版本。  
  
4.  移动\\ **bin**目录到在步骤 2 中创建的目录。  
  
5.  启动图形工具 MageUI.exe。  
  
    ```  
    MageUI.exe  
    ```  
  
6.  通过选择创建一个新的应用程序清单**文件**，**新建**，**应用程序清单**从菜单。  
  
7.  默认值上**名称**选项卡上，输入此部署的名称和版本数。 此外，请提供的值**发布服务器**，它将作为使用开始菜单中的应用程序的快捷方式链接的文件夹名称为在部署时。  
  
8.  选择**应用程序选项**选项卡，单击**将应用程序清单信任信息用于**。 这将启用第三方品牌此[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]应用程序。  
  
9. 选择**文件**选项卡，单击**浏览**应用程序目录文本框旁边的按钮。  
  
10. 选择包含你在步骤 2 中创建的应用程序文件的目录，然后单击**确定**文件夹选择对话框上。  
  
11. 单击**填充**按钮以将所有应用程序文件添加到文件列表。 如果你的应用程序包含多个可执行文件，通过选择标记为启动应用此部署的主要可执行文件**入口点**从**文件类型**下拉列表。 （如果你的应用程序仅包含一个可执行文件，MageUI.exe 将将其标记为你。）  
  
12. 选择**所需权限**选项卡上，然后选择需要你的应用程序要断言的信任级别。 默认值是**完全信任**，这将是适用于大多数应用程序。  
  
13. 选择**文件**，**保存**从菜单中，并保存应用程序清单。 系统将提示你时将其保存对应用程序清单进行签名。  
  
14. 如果必须将证书作为文件系统上的文件存储，使用**作为证书文件签名**选项，然后从使用省略号的文件系统中选择证书 (**...**) 按钮。  
  
     -或-  
  
     如果你的证书保存在可以从你的计算机访问的证书存储区中，选择**签名存储的证书选项**，然后从提供的列表中选择的证书。  
  
15. 选择**文件**，**新建**，**部署清单**从创建部署清单，该菜单，然后在**名称**选项卡上，提供名称和版本号 (**1.0.0.0**在此示例中)。  
  
16. 切换到**更新**选项卡，然后指定你希望此应用程序的更新的频率。 如果你的应用程序使用[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]部署 API 以检查是否更新自身，清除复选框标记为**此应用程序应检查更新**。  
  
17. 切换到**应用程序引用**选项卡。可以通过单击预填充此选项卡上的值的所有**选择清单**在前面的步骤中创建按钮，然后选择应用程序清单。  
  
18. 选择**保存**并将部署清单保存到磁盘。 系统将提示你时将其保存对应用程序清单进行签名。 单击**取消**保存清单，而无需对它的签名。  
  
19. 向客户提供所有应用程序文件。  
  
20. 此时，客户必须与自己自行生成的证书的部署清单签名。 例如，如果客户适用于名为 Adventure Works 的公司，他可以生成自签名的证书通过 MakeCert.exe 工具。 接下来，使用 Pvk2pfx.exe 工具组合到 PFX 文件，可传递给 MageUI.exe 通过 MakeCert.exe 创建的文件。  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. 生成的证书，客户现在签名的部署清单通过在 MageUI.exe 中打开部署清单，然后保存它。 当出现签名对话框中时，客户选择**作为证书文件签名**选项，并选择他已经保存在磁盘的 PFX 文件。  
  
22. 客户部署到其用户应用程序。  
  
## <a name="next-steps"></a>后续步骤  
  
## <a name="see-also"></a>请参阅  
 [Mage.exe（清单生成和编辑工具）](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe（图形化客户端中的清单生成和编辑工具）](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [MakeCert](https://msdn.microsoft.com/library/windows/desktop/aa386968.aspx)