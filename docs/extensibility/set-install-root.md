---
title: 使用 VSIX v3 扩展文件夹外安装 |Microsoft Docs
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 913c3745-8aa9-4260-886e-a05aecfb2225
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 847ce9bc55e93f292ffdfe6f237e8c39eeac9fd4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53968493"
---
# <a name="installing-outside-the-extensions-folder"></a>在扩展文件夹外安装

从 Visual Studio 2017 和 VSIX v3 （版本 3），现在支持用于安装扩展文件夹外的扩展资产。 目前，作为有效的安装位置 （其中 [INSTALLDIR] 映射到 Visual Studio 实例的安装目录），会启用以下位置：

* [INSTALLDIR] \MSBuild
* [INSTALLDIR] \Xml\Schemas
* [INSTALLDIR] \Common7\IDE\PublicAssemblies
* [INSTALLDIR] \Licenses
* [INSTALLDIR] \Common7\IDE\ReferenceAssemblies
* [INSTALLDIR] \Common7\IDE\RemoteDebugger
* [INSTALLDIR] \Common7\IDE\VC\VCTargets

>**注意：** VSIX 格式不允许您安装 VS 安装文件夹结构之外。

为了支持安装到这些目录，必须在 VSIX 安装"每个实例每台计算机"。 可以通过检查 extension.vsixmanifest 设计器中的"所有用户"复选框来启用此选项：

![检查所有用户](media/check-all-users.png)

## <a name="how-to-set-the-installroot"></a>如何设置 InstallRoot

若要设置的安装目录，可以使用**属性**Visual Studio 窗口中的。 例如，可以设置`InstallRoot`到上述位置之一的项目引用的属性：

![安装根属性](media/install-root-properties.png)

这会将一些元数据添加到相应`ProjectReference`VSIX 项目的.csproj 文件内的属性：

```xml
 <ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
        <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
        <Name>ClassLibrary1</Name>
        <InstallRoot>PublicAssemblies</InstallRoot>
 </ProjectReference>
```

>**注意：** 如果您愿意，可以直接编辑.csproj 文件。

## <a name="how-to-set-a-subpath-under-the-installroot"></a>如何设置下 InstallRoot 子路径

如果想要安装到子路径下`InstallRoot`，就可以通过设置`VsixSubPath`属性一样`InstallRoot`属性。 例如，假设我们想要安装到我们的项目引用的输出 [INSTALLDIR]\MSBuild\MyCompany\MySDK\1.0。 轻松地使用属性设计器，我们可以执行此操作：

![设置子路径](media/set-subpath.png)

相应的.csproj 更改将如下所示：

```xml
<ProjectReference Include="..\ClassLibrary1\ClassLibrary1.csproj">
       <Project>{69a979f1-eba2-43e7-9346-0e56e803508b}</Project>
       <Name>ClassLibrary1</Name>
       <InstallRoot>MSBuild</InstallRoot>
       <VSIXSubPath>MyCompany\MySDK\1.0</VSIXSubPath>
</ProjectReference>
```

## <a name="extra-information"></a>额外信息

属性设计器更改应用到多个只是项目的引用;可以设置`InstallRoot`内你的项目的项元数据 （使用上文所述的相同方法）。
