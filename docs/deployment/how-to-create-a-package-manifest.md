---
title: 如何： 创建程序包清单 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- package files [Windows Installer]
- package files [ClickOnce]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper packages
ms.assetid: 5aecc507-2764-42f2-ae6f-c227971cf0af
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4cf0d92169974970c041214e53f8a8feb5f07a24
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56598032"
---
# <a name="how-to-create-a-package-manifest"></a>如何：创建程序包清单
若要部署应用程序的先决条件，你可以使用引导程序包。 引导程序包包含一个单一产品清单文件，但是包清单的每个区域设置。 在不同的本地化版本之间共享的功能应进入产品清单。

 有关包清单的详细信息，请参阅[如何： 创建产品清单](../deployment/how-to-create-a-product-manifest.md)。

## <a name="create-the-package-manifest"></a>创建程序包清单

#### <a name="to-create-the-package-manifest"></a>若要创建程序包清单

1.  创建引导程序包的目录。 此示例使用*C:\package*。

2.  如使用的区域设置的名称创建一个子目录*en*为英语。

3.  在 Visual Studio 中，创建名为一个 XML 文件*package.xml*，并将其保存到*C:\package\en*文件夹。

4.  添加 XML 以列出引导程序包的名称、 此本地化的包清单和可选的许可协议的区域性。 下面的 XML 使用的变量`DisplayName`和`Culture`，其定义中的更高版本的元素。

    ```xml
    <Package
        xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
        Name="DisplayName"
        Culture="Culture"
        LicenseAgreement="eula.txt">
    ```

5.  添加 XML 以列出特定于区域设置的目录中的所有文件。 下面的 XML 使用名为的文件*eula.txt*适用于**en**区域设置。

    ```xml
    <PackageFiles>
      <PackageFile Name="eula.txt"/>
    </PackageFiles>
    ```

6.  添加 XML 以定义引导程序包可本地化的字符串。 以下 XML 添加错误字符串**en**区域设置。

    ```xml
      <Strings>
        <String Name="DisplayName">Custom Bootstrapper Package</String>
        <String Name="CultureName">en</String>
        <String Name="NotAnAdmin">You must be an administrator to install
    this package.</String>
        <String Name="GeneralFailure">A general error has occurred while
    installing this package.</String>
    </Strings>
    ```

7.  复制*C:\package*到 Visual Studio 引导程序目录的文件夹。 对于 Visual Studio 2010 中，这是*\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages*目录。

## <a name="example"></a>示例
 包清单包含特定于区域设置的信息，如错误消息、 软件许可条款和语言包。

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Package
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
  Name="DisplayName"
  Culture="Culture"
  LicenseAgreement="eula.txt">

  <PackageFiles>
    <PackageFile Name="eula.txt"/>
  </PackageFiles>

  <Strings>
    <String Name="DisplayName">Custom Bootstrapper Package</String>
    <String Name="Culture">en</String>
    <String Name="NotAnAdmin">You must be an administrator to install this package.</String>
    <String Name="GeneralFailure">A general error has occurred while
installing this package.</String>
  </Strings>
</Package>
```

## <a name="see-also"></a>请参阅
- [产品和包架构引用](../deployment/product-and-package-schema-reference.md)