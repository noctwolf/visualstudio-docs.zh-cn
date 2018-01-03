---
title: "Visual Studio Tools for Unity Azure 演练连接 | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516A8FB2-8DFF-4BAB-8116-FDCD1C228DB3
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: cb2ce447f21231b98d6464824ba7d088fee16cce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="test-the-client-connection"></a>测试客户端连接

AzureMobileServiceClient 单一实例已创建完成，现在开始测试客户端连接。

## <a name="create-the-testclientconnection-script"></a>创建 TestClientConnection 脚本

1. 在 Unity 的 **Scripts** 文件夹中，创建一个名为 **TestClientConnection** 的新 C# 脚本。

2. 在 Visual Studio 中打开该脚本，删除所有模板代码，并添加以下代码：

  ```csharp
  using System.Collections.Generic;
  using UnityEngine;
  using System.Threading.Tasks;
  using System;
  using System.Linq;
  using Microsoft.WindowsAzure.MobileServices;

  public class TestClientConnection : MonoBehaviour
  {
      void Start()
      {
          Task.Run(TestTableConnection);
      }

      private async Task TestTableConnection()
      {
          var table = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

          Debug.Log("Testing ToListAsync...");
          await TestToListAsync(table);

          Debug.Log("Testing InsertAsync...");
          await TestInsertAsync(table);

          Debug.Log("Testing DeleteAsync...");
          await TestDeleteAsync(table);

          Debug.Log("All testing complete.");
      }

      private async Task TestInsertAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await TestToListAsync(table);
              var initialCount = allEntries.Count();

              await table.InsertAsync(new CrashInfo { X = 1, Y = 2, Z = 3 });

              allEntries = await TestToListAsync(table);
              var newCount = allEntries.Count();

              Debug.Assert(newCount == initialCount + 1, "InsertAsync failed!");
          }
          catch (Exception)
          {
              throw;
          }
      }

      private async Task<List<CrashInfo>> TestToListAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await table.ToListAsync();
              Debug.Assert(allEntries != null, "ToListAsync failed!");
              return allEntries;
          }
          catch (Exception)
          {

              throw;
          }
      }

      private async Task TestDeleteAsync(IMobileServiceTable<CrashInfo> table)
      {
          var allEntries = await TestToListAsync(table);

          foreach (var item in allEntries)
          {
              try
              {
                  await table.DeleteAsync(item);
              }
              catch (Exception)
              {
                  throw;
              }
          }

          allEntries = await TestToListAsync(table);

          Debug.Assert(allEntries.Count() == 0, "DeleteAsync failed!");
      }
  }
  ```

3. 在 Unity 的“GameObject”菜单中，选择“GameObject”>“创建空白项”，在 Unity 场景中创建空的 GameObject。 将其重命名为 **TestClientConnection**。

4. 将 TestClientConnection 脚本从 Unity 的“项目”窗口**拖到**“层次结构”窗口中的 TestClientConnection GameObject 上。

5. 在 Unity 菜单中，选择“文件”>“将场景另存为...”。将场景命名为“客户端连接测试”并单击“保存”。

5. 单击 Unity 中的“播放”按钮，观察控制台窗口。 确保没有失败的断言。

6. 打开 Azure 门户上的 CrashInfo 简易表。 它现在应包含一个值为**（1、2、3）**的 **X、Y、Z** 坐标条目以及一个值为 **true** 的 **deleted** 列。 每次运行测试时，都应当向表中添加一个值相同但 ID 唯一的新条目。

  ![简易表条目](media/vstu_azure-test-client-connection-image1.png)

## <a name="next-step"></a>下一步
* [导入示例游戏资产](visual-studio-tools-for-unity-azure-game-assets.md)。
