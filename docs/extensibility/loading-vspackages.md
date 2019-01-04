---
title: 加载 VSPackages |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, loading
ms.assetid: f4c3dcea-5051-4065-898f-601269649d92
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 477ac9b0b97a7544402f0f70204b8ecf7b43ba95
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53925824"
---
# <a name="load-vspackages"></a>加载 Vspackage
Vspackage 加载到 Visual Studio 中，仅当其功能是必需的。 例如，加载 VSPackage 时 Visual Studio 使用项目工厂或 VSPackage 实现的服务。 此功能被称为延迟的加载，这尽可能使用以提高性能。  
  
> [!NOTE]
>  Visual Studio 可以确定某些 VSPackage 信息，例如 VSPackage 提供，而不加载 VSPackage 的命令。  
  
 Vspackage 可以设置为自动加载在特定的用户界面 (UI) 上下文中，例如，打开解决方案时。 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute>属性将设置此上下文中。  
  
### <a name="autoload-a-vspackage-in-a-specific-context"></a>自动加载 VSPackage 的特定上下文中  
  
-   添加`ProvideAutoLoad`VSPackage 属性的属性：  
  
    ```csharp  
    [DefaultRegistryRoot(@"Software\Microsoft\VisualStudio\14.0")]  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [ProvideAutoLoad(UIContextGuids80.SolutionExists)]  
    [Guid("00000000-0000-0000-0000-000000000000")] // your specific package GUID  
    public class MyAutoloadedPackage : Package  
    {. . .}  
    ```  
  
     请参阅的枚举的字段<xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80>有关 UI 上下文及其 GUID 值的列表。  
  
-   中设置断点<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>方法。  
  
-   生成 VSPackage 并启动调试。  
  
-   加载解决方案或创建一个。  
  
     VSPackage 加载，并在断点处停止。  
  
## <a name="force-a-vspackage-to-load"></a>强制 VSPackage 加载  
 在某些情况下可能需要强制另一个 VSPackage 加载 VSPackage。 例如，轻型 VSPackage 可能会加载更大 VSPackage 中不能作为 CMDUIContext 的上下文。  
  
 可以使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackage%2A>方法，以强制 VSPackage 加载。  
  
-   插入此代码<xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A>强制另一个 VSPackage 加载的 vspackage 的方法：  
  
    ```csharp  
    IVsShell shell = GetService(typeof(SVsShell)) as IVsShell;  
    if (shell == null) return;  
  
    IVsPackage package = null;  
    Guid PackageToBeLoadedGuid =   
        new Guid(Microsoft.PackageToBeLoaded.GuidList.guidPackageToBeLoadedPkgString);  
    shell.LoadPackage(ref PackageToBeLoadedGuid, out package);  
  
    ```  
  
     初始化 VSPackage 时，它会强制`PackageToBeLoaded`加载。  
  
     强制加载不应该用于 VSPackage 通信。 使用[使用，并提供服务](../extensibility/using-and-providing-services.md)相反。
  
## <a name="see-also"></a>请参阅  
 [VSPackage](../extensibility/internals/vspackages.md)
