---
title: "Visual Studio Tools for Unity Azure 演练数据模型 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6FCCA8D1-0D06-4B2A-A55F-FC3D1FEA0F56
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: e3b6064a3947f57ffcbe6422162c6c72fca0ab21
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="create-data-model-classes"></a>创建数据模型类

Unity 项目必须包含与在 Azure 移动应用后端中创建的表一致的数据模型类。

## <a name="create-the-crashinfo-class"></a>创建 CrashInfo 类

1. 在 Unity 中，在根 **Assets** 目录中添加一个名为 **Scripts** 的新文件夹。 在新的 Scripts 文件夹中，创建另一个名为 **Data Models** 的新文件夹。 这仅用于进行组织。

2. 在新的 Data Models 文件夹中，创建一个名为 **CrashInfo** 的新 C# 脚本。

3. 打开新的 `CrashInfo` 脚本，删除任何模板代码（包括类声明和 using 语句），并添加以下内容：

  ```csharp
  public class CrashInfo
  {
      public string Id { get; set; }
      public float X { get; set; }
      public float Y { get; set; }
      public float Z { get; set; }
  }
  ```

  > [!WARNING]
  > 若要使演练正常工作，数据模型类的名称必须与在 Azure 移动应用后端上创建的简易表的名称匹配。

## <a name="create-the-highscoreinfo-class"></a>创建 HighScoreInfo 类

1. 在 Data Models 文件夹中，创建一个名为 **HighScoreInfo** 的新 C# 脚本。

2. 打开新的 `HighScoreInfo` 脚本，删除任何模板代码（包括类声明和 using 语句），并添加以下内容：

  ```csharp
  public class HighScoreInfo
  {
      public string Name { get; set; }
      public float Time { get; set; }
      public string Id { get; set; }
  }
  ```

  ## <a name="next-step"></a>下一步

  * [实现 Azure MobileServiceClient](visual-studio-tools-for-unity-azure-mobile-client.md)
