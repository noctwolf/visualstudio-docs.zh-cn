---
title: VBA 的访问权限创建/打开 VSTO system 项目
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office system project
titleSuffix: Visual Studio Tools for Microsoft Office
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c85a907b057118c28ea35b8a920337ecdad5ad01
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177652"
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>启用对 VBA 创建或打开 Visual Studio Tools for the Microsoft Office system 项目的访问

可以创建或打开 Visual Studio Tools for the Microsoft Office system 项目之前，必须显式启用对 Visual Basic for Applications (VBA) 项目系统在 Microsoft Office 中的访问权限。

 Microsoft Office 开发项目需要访问 Visual Basic for Applications (VBA) 项目系统在 Microsoft Office Word 和 Microsoft Office Excel 中，即使项目的应用程序不使用 Visual Basic。 Visual Basic 和 C# 项目中控件的设计时支持均需依赖 Visual Basic for Applications 项目系统。

 有些 Microsoft Office 宏病毒会尝试自动运行 Visual Basic for Applications 项目系统来进行传播。 如果启用对 Visual Basic for Applications 项目系统的访问，就失去了帮助防止宏病毒传播的安全保护。 不过，由于正常的宏安全性设置仍然起作用，因此你为 Office 应用程序维护的宏安全级别和受信任的发行者列表将确定是否有任何宏可以在计算机上运行。

> [!NOTE]
> 这仅适用于开发计算机。 最终用户计算机无需启用此选项即可运行 Office 解决方案。

 值得注意的是，如果计算机此前已经感染宏病毒，则禁用对 Visual Basic for Applications 项目系统的访问本身并不会防止感染病毒，而只能帮助阻止某些病毒传播到其他文档。 默认情况下该选项为禁用状态，从而为你的计算机提供一层额外保护，但如果遵循以下最佳安全做法，即使启用该选项，也不会使你的计算机更易受病毒感染。

 针对 Office 宏病毒是高或极高安全级别，以只信任来自的宏在运行 Office 验证，已知的源，并及时更新安全修补程序和病毒扫描程序的最佳保护。

 可以启用或禁用该选项**信任 Visual Basic 项目的访问**手动。

 如果看到 VBA 或 COM 错误，则可以修复 Office 的安装。

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>若要启用或禁用对 Visual Basic 项目的访问

1. 单击 **“文件”** 选项卡。

2. 单击“选项” 。

3. 单击**信任中心**，然后单击**信任中心设置**。

4. 在中**信任中心**，单击**宏设置**。

5. 选中或取消选中**信任对 VBA 工程对象模型访问**启用或禁用对 Visual Basic 项目的访问。

6. 单击 **“确定”** 。

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>若要启用或禁用对 2007 Microsoft Office system 的 Visual Basic 项目的访问

1. 上**工具**菜单在 Word 或 Excel 中，依次指向**宏**，然后单击**安全**。

2. 在中**安全**对话框中，单击**受信任的发行者**选项卡。

3. 若要启用，或清除要禁用，请选择**信任 Visual Basic 项目的访问**。

4. 单击 **“确定”** 。

## <a name="to-set-your-office-macro-security-level"></a>设置 Office 宏安全级别

1. 单击 **“文件”** 选项卡。

2. 单击“选项” 。

3. 单击**信任中心**，然后单击**信任中心设置**。

4. 在中**信任中心**，单击**宏设置**。

5. 在中**宏设置**部分中，选择所需的设置。

6. 单击 **“确定”** 。

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>若要设置 Office 宏安全级别与 2007 Microsoft Office system

1. 上**工具**菜单在 Word 或 Excel 中，依次指向**宏**，然后单击**安全**。

2. 上**安全级别**选项卡上，选择所需的设置。

    **安全级别**选项卡包含有关每个级别的详细信息。 有关详细信息，请参阅“Office 帮助”中的“宏安全级”主题。

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>通过 2007 Microsoft Office 系统安装 VBA

1. 在控制面板中，运行**添加或删除程序**或**程序和功能**。

2. 选择中的 Office**当前安装的程序**列表。

3. 单击“更改” 。

4. 选择**添加或删除功能**，然后单击**继续**。

5. 选择**选择高级应用程序的自定义**，然后单击**下一步**。

6. 展开**Office 共享功能**中**应用程序和工具的选择更新选项**列表。

7. 打开下拉列表菜单旁边**应用程序的 Visual Basic**，然后单击**从我的电脑上运行**。

8. 单击 **“继续”** 。

9. 单击 **“关闭”** 。

## <a name="to-repair-your-installation-of-office"></a>修复 Office 安装

1. 在控制面板中，运行**添加或删除程序**或**程序和功能**。

2. 选择您的中的 Office 版本**当前安装的程序**列表。

3. 单击“更改” 。

4. 选择**重新安装或修复**，然后单击**下一步**。

5. 选择**检测并修复 Office 安装中的错误**，然后单击**安装**。

## <a name="see-also"></a>请参阅
- [保护 Office 解决方案](../vsto/securing-office-solutions.md)
